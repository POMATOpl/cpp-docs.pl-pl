---
description: 'Dowiedz się więcej na temat: TN040: MFC/OLE In-Place zmiana rozmiaru i powiększanie'
title: 'TN040: MFC-OLE In-Place zmiana rozmiaru i powiększanie'
ms.date: 11/04/2016
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: e21b70dc10ee467f94386880255287218a3b6e99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215394"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE — zmienianie rozmiaru i powiększanie w miejscu

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga omawia problemy związane z edycją w miejscu oraz sposób, w jaki serwer powinien spełnić prawidłowe powiększanie i zmianę rozmiaru w miejscu. W przypadku aktywacji w miejscu pojęcie WYSIWYG jest podejmowane krok po kroku w tym, że kontenery i serwery współpracują ze sobą, a zwłaszcza interpretują specyfikację OLE w taki sam sposób.

Ze względu na bliską interakcję między kontenerem i serwerem obsługującym aktywację w miejscu istnieje wiele oczekiwań od użytkownika końcowego, który powinien być utrzymywany:

- Prezentacja prezentacji (metaplik rysowany w `COleServerItem::OnDraw` przesłonięciu) powinna wyglądać dokładnie tak samo, jak w przypadku rysowania do edycji (z tą różnicą, że narzędzia do edycji nie są widoczne).

- Gdy rozmiar kontenera zostanie powiększony, okno serwera powinno być.

- Zarówno kontener, jak i serwer powinny wyświetlać obiekty do edycji przy użyciu tych samych metryk. Oznacza to użycie trybu mapowania na podstawie liczby pikseli *logicznych* na cal — nie do pikseli fizycznych na cal podczas renderowania na urządzeniu wyświetlającym.

> [!NOTE]
> Ponieważ aktywacja w miejscu ma zastosowanie tylko do elementów osadzonych (niepołączonych), powiększanie dotyczy tylko obiektów osadzonych. Zostaną wyświetlone interfejsy API w obu `COleServerDoc` i `COleServerItem` , które są używane do powiększania. Przyczyną tego dichotomy jest to, że tylko funkcje, które są prawidłowe dla elementów połączonych i osadzonych, są w `COleServerItem` (to pozwala na posiadanie wspólnej implementacji) i funkcje, które są prawidłowe tylko dla obiektów osadzonych, znajdują się w `COleServerDoc` klasie (z perspektywy serwera, jest to **dokument** osadzony).

Większość obciążeń jest umieszczana w implementacji serwera, w tym przypadku serwer musi mieć świadomość współczynnika powiększenia kontenera i zmodyfikować jego interfejs edycji odpowiednio do potrzeb. Ale w jaki sposób serwer określa współczynnik powiększenia używany przez kontener

## <a name="mfc-support-for-zooming"></a>Obsługa MFC w celu powiększania

Bieżący współczynnik powiększenia można określić, wywołując metodę `COleServerDoc::GetZoomFactor` . Wywoływanie tego elementu, gdy dokument nie jest aktywny, będzie zawsze powodował współczynnik powiększenia 100% (lub współczynnik 1:1). Wywołanie go w aktywnym miejscu może zwrócić coś innego niż 100%.

Aby zapoznać się z przykładem prawidłowego powiększania, zobacz przykład OLE MFC [HIERSVR](../overview/visual-cpp-samples.md). Powiększanie w HIERSVR jest skomplikowane przez fakt, że wyświetla tekst, a tekst, ogólnie, nie skaluje się w sposób liniowy (wskazówki, konwencje typograficzne, szerokości projektu i wysokości wszystkie komplikują kwestię). Nadal, HIERSVR jest rozsądne odwołanie do prawidłowego wdrożenia powiększania, a więc jest [to samouczek](../overview/visual-cpp-samples.md) samouczka MFC (krok 7).

`COleServerDoc::GetZoomFactor` Określa współczynnik powiększenia na podstawie wielu różnych metryk dostępnych zarówno z kontenera, `COleServerItem` jak i z implementacji `COleServerDoc` klas i. W skrócie bieżący współczynnik powiększenia jest określany na podstawie następującej formuły:

```
Position Rectangle (PR) / Container Extent (CE)
```

PROSTOKĄT położenia jest określany przez kontener. Jest on zwracany do serwera podczas aktywacji w miejscu `COleClientItem::OnGetItemPosition` , gdy jest wywoływana i jest aktualizowany, gdy kontener wywoła serwer `COleServerDoc::OnSetItemRects` (z wywołaniem do `COleClientItem::SetItemRects` ).

ZAKRES kontenera jest nieco bardziej skomplikowany do obliczenia. Jeśli kontener został wywołany `COleServerItem::OnSetExtent` (z wywołaniem `COleClientItem::SetExtent` ), zakres kontenera to ta wartość konwertowana na piksele na podstawie liczby pikseli na cal logiczny. Jeśli kontener nie został wywołany jako setSize (zazwyczaj jest to przypadek), zakres kontenera jest rozmiarem zwracanym z `COleServerItem::OnGetExtent` . Dlatego, jeśli kontener nie został wywołany jako setstop, struktura zakłada, że jeśli został on wywołany przez kontener z 100% rozmiaru naturalnego (wartość zwrócona z `COleServerItem::GetExtent` ). Inna metoda polega na tym, że kontener wyświetla 100% (nie więcej, nie mniej) elementu.

Należy pamiętać, że chociaż `COleServerItem::OnSetExtent` i `COleServerItem::OnGetExtent` mają podobne nazwy, nie manipulują tym samym atrybutem elementu. `OnSetExtent` jest wywoływana, aby umożliwić serwerowi określenie, jaka część obiektu jest widoczna w kontenerze (niezależnie od współczynnika powiększenia) i `OnGetExtent` jest wywoływana przez kontener w celu określenia idealnego rozmiaru obiektu.

Analizując poszczególne interfejsy API, możesz uzyskać wyraźniejszy obraz:

## <a name="coleserveritemongetextent"></a>COleServerItem:: OnGetExtent

Ta funkcja powinna zwracać "rozmiar naturalny" w jednostkach HIMETRIC elementu. Najlepszym sposobem na określenie "rozmiaru naturalnego" jest zdefiniowanie go jako rozmiaru, który może pojawić się podczas drukowania. Zwrócony tutaj rozmiar jest stałą dla konkretnej zawartości elementu (podobnie jak metaplik, który jest stały dla określonego elementu). Ten rozmiar nie zmienia się, gdy do elementu jest stosowane powiększanie. Zwykle nie zmienia się, gdy kontener przekazuje element więcej lub mniej miejsca przez wywołanie `OnSetExtent` . Przykładem zmiany może być prosty edytor tekstu bez możliwości "Margin", który zawinięty tekst w oparciu o ostatni zakres Wysłany przez kontener. Jeśli serwer zostanie zmieniony, serwer powinien prawdopodobnie ustawić bit OLEMISC_RECOMPOSEONRESIZE w rejestrze systemowym (zobacz dokumentację zestawu OLE SDK, aby uzyskać więcej informacji na temat tej opcji).

## <a name="coleserveritemonsetextent"></a>COleServerItem:: OnSetExtent

Ta funkcja jest wywoływana, gdy kontener pokazuje "więcej lub mniej" obiektu. Większość kontenerów nie wywoła tego w ogóle. Domyślna implementacja przechowuje ostatnią wartość odebraną z kontenera w "m_sizeExtent", która jest używana `COleServerDoc::GetZoomFactor` podczas obliczania wartości zakresu kontenera opisanej powyżej.

## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects

Ta funkcja jest wywoływana tylko wtedy, gdy dokument jest aktywny. Jest wywoływana, gdy kontener aktualizuje położenie elementu lub wycinka zastosowany do elementu. PROSTOKĄT położenia, jak wspomniano powyżej, zawiera licznik dla obliczenia współczynnika powiększenia. Serwer może zażądać zmiany pozycji elementu przez wywołanie `COleServerDoc::RequestPositionChange` . Kontener może lub nie odpowiada na to żądanie przez wywołanie metody `OnSetItemRects` (z wywołaniem do `COleServerItem::SetItemRects` ).

## <a name="coleserverdocondraw"></a>COleServerDoc:: OnDraw

Ważne jest, aby pamiętać, że metaplik utworzony przez zastąpienie elementu `COleServerItem::OnDraw` generuje dokładnie ten sam metaplik, niezależnie od bieżącego współczynnika powiększenia. Kontener odpowiednio skaluje metaplik. Jest to ważna różnica między widokiem `OnDraw` a elementem serwera `OnDraw` . Widok obsługuje powiększanie, a element po prostu tworzy metaplik *powiększony* i pozostawia go do kontenera, aby wykonać odpowiednie powiększanie.

Najlepszym sposobem, aby upewnić się, że serwer działa prawidłowo, to użycie implementacji, `COleServerDoc::GetZoomFactor` Jeśli dokument jest aktywny.

## <a name="mfc-support-for-in-place-resizing"></a>Obsługa MFC dla In-Place zmiany rozmiarów

MFC w pełni implementuje interfejs w miejscu zmiany rozmiarów, zgodnie z opisem w specyfikacji OLE 2. Interfejs użytkownika jest obsługiwany przez `COleResizeBar` klasę, niestandardową wiadomość WM_SIZECHILD i specjalną obsługę tego komunikatu w programie `COleIPFrameWnd` .

Możesz chcieć zaimplementować inną obsługę tego komunikatu niż to, co jest dostarczane przez platformę. Jak opisano powyżej, struktura pozostawia wyniki zmiany rozmiaru w miejscu do kontenera — serwer reaguje na zmianę współczynnika powiększenia. Jeśli kontener reaguje przez ustawienie zakresu kontenera i PROSTOKĄTa położenia podczas przetwarzania jego `COleClientItem::OnChangeItemPosition` (wywołanego jako wynik wywołania `COleServerDoc::RequestPositionChange` ), zmiana rozmiaru w miejscu spowoduje wyświetlenie "więcej lub mniej" elementu w oknie edycji. Jeśli kontener reaguje przez samo ustawienie PROSTOKĄTa położenia podczas przetwarzania `COleClientItem::OnChangeItemPosition` , współczynnik powiększenia zmieni się, a element będzie pokazywany jako "powiększone" lub "out".

Serwer może kontrolować (w pewnym stopniu) co się dzieje w trakcie tej negocjacji. Na przykład w arkuszu kalkulacyjnym może być wyświetlany więcej lub mniej komórek, gdy użytkownik zmienia rozmiar okna podczas edytowania elementu w miejscu. Edytor wyrazów może wybrać zmianę "marginesów strony", tak aby były one takie same jak okno i przewinąć tekst do nowego marginesu. Serwery implementują to przez zmianę zakresu naturalnego (rozmiar zwrócony z `COleServerItem::OnGetExtent` ) po zakończeniu zmiany rozmiaru. Spowoduje to, że zarówno prostokąt położenia, jak i zakres kontenera mogą ulec zmianie o tej samej wartości, co skutkuje tym samym współczynnikiem powiększenia, ale większym lub mniejszym obszarem wyświetlania. Ponadto większy lub mniejszy dokument będzie widoczny w metapliku wygenerowanym przez `OnDraw` . W takim przypadku sam dokument ulega zmianie, gdy użytkownik zmieni rozmiar elementu, a nie tylko w obszarze wyświetlania.

Można zaimplementować niestandardowe zmiany rozmiarów i nadal korzystać z interfejsu użytkownika dostarczonego przez `COleResizeBar` zastąpienie komunikatu WM_SIZECHILD w `COleIPFrameWnd` klasie. Aby uzyskać więcej informacji na temat WM_SIZECHILD, zobacz [Uwagi techniczne 24](../mfc/tn024-mfc-defined-messages-and-resources.md).

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
