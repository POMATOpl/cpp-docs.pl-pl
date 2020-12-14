---
description: 'Dowiedz się więcej o: TN029: rozdzielacz Windows'
title: 'TN029: okna podziału'
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: e1079adf403b64aa47f5aae00aa32f7da702ddcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215641"
---
# <a name="tn029-splitter-windows"></a>TN029: okna podziału

Ta Uwaga opisuje klasę MFC [CSplitterWnd](../mfc/reference/csplitterwnd-class.md), która zapewnia podział okna i zarządza zmianą rozmiarów innych okien okien.

## <a name="splitter-styles"></a>Style rozdzielacza

A `CSplitterWnd` obsługuje dwa różne style dzielenia okien.

W obszarze "rozdzielacze statyczne" okno rozdzielacza tworzy utworzone okienka. Kolejność i liczba okienek nigdy nie zmieniają się. Paski podziału są używane do zmiany rozmiaru różnych okienek. Możesz użyć tego stylu do wyświetlania różnej klasy widoku w każdym okienku. Edytor grafiki Visual C++ i Menedżer plików systemu Windows to przykłady programów korzystających z tego stylu rozdzielacza. Ten styl okna rozdzielacza nie używa pól rozdzielacza.

W obszarze "rozdzielacze dynamiczne" dodatkowe okienka są tworzone i niszczone, gdy użytkownik podzieli i oddzieli nowe widoki. Ten rozdzielacz rozpoczyna się z pojedynczym widokiem i udostępnia pola rozdzielacza, aby użytkownik mógł zainicjować podział. Okno rozdzielacza dynamicznie tworzy nowy obiekt widoku, gdy widok jest podzielony w jednym kierunku. Ten nowy obiekt widoku reprezentuje nowe okienko. Jeśli widok jest podzielony na dwa kierunki przy użyciu interfejsu klawiatury, okno rozdzielacza tworzy trzy nowe obiekty widoku dla trzech nowych okienek. Gdy podział jest aktywny, system Windows wyświetla pole rozdzielacza jako pasek podziału między okienkami. System Windows niszczy dodatkowe obiekty widoku, gdy użytkownik usuwa podział, ale oryginalny widok pozostaje do momentu zniszczenia samego okna rozdzielacza. Microsoft Excel i Microsoft Word są przykładami aplikacji, które używają dynamicznego stylu rozdzielacza.

Podczas tworzenia dowolnego rodzaju okna rozdzielacza należy określić maksymalną liczbę wierszy i kolumn, którymi będzie zarządzać rozdzielacz. Statyczny rozdzielacz utworzy okienka, aby wypełnić wszystkie wiersze i kolumny. Dynamiczny rozdzielacz utworzy tylko pierwsze okienko po `CSplitterWnd` utworzeniu.

Maksymalna liczba okienek, które można określić dla rozdzielaczy statycznej, to 16 wierszy na 16 kolumn. Zalecane konfiguracje są następujące:

- 1 wiersz x 2 kolumny: zwykle z niepodobnymi okienkami

- 2 wiersze x 1 kolumna: zwykle z niepodobnymi okienkami

- 2 wiersze x 2 kolumny: zwykle z podobnymi okienkami

Maksymalna liczba okienek, które można określić dla rozdzielaczy dynamiczne, to 2 wiersze o 2 kolumnach. Zalecane konfiguracje są następujące:

- 1 wiersz x 2 kolumny: dla danych kolumnowy

- 2 wiersze x 1 kolumna: dla danych tekstowych lub innych

- 2 wiersze x 2 kolumny: dla danych z siatką lub tabelą

## <a name="splitter-examples"></a>Przykłady rozdzielacza

Wiele programów przykładowych MFC używa okien rozdzielacza bezpośrednio lub pośrednio. Ogólna Przykładowa [VIEWEX](../overview/visual-cpp-samples.md) MFC ilustruje kilka zastosowania rozdzielaczy static, w tym sposób umieszczania rozdzielacza w rozdzielaczu.

Możesz również użyć ClassWizard, aby utworzyć nową klasę okna ramki podrzędnej wielu dokumentów (MDI), która zawiera okno rozdzielacza. Aby uzyskać więcej informacji na temat rozdzielacza systemu Windows, zobacz [wiele typów dokumentów, widoków i okien ramowych](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="terminology-used-by-implementation"></a>Terminologia używana przez implementację

Poniżej znajduje się lista warunków, które są specyficzne dla okien rozdzielacza:

`CSplitterWnd`: Okno, które udostępnia kontrolki dzielenia okienka i paski przewijania, które są współużytkowane przez wszystkie okienka w wierszu lub kolumnie. Należy określić wiersze i kolumny zawierające cyfry zerowe (pierwsze okienko to wiersz = 0 i kolumna = 0).

Okienko: specyficzne dla aplikacji okno, które `CSplitterWnd` zarządza. Okienko zazwyczaj jest obiektem, który jest wyprowadzany z [klasy CView](../mfc/reference/cview-class.md), ale może być dowolnym obiektem [CWnd](../mfc/reference/cwnd-class.md) , który ma odpowiedni identyfikator okna podrzędnego.

Aby użyć `CWnd` obiektu pochodnego, przekaż RUNTIME_CLASS obiektu do `CreateView` funkcji tak samo, jak w przypadku korzystania z `CView` klasy pochodnej. Klasa musi używać DECLARE_DYNCREATE i IMPLEMENT_DYNCREATE, ponieważ struktura używa tworzenia dynamicznego w czasie wykonywania. Chociaż istnieje wiele kodów, `CSplitterWnd` które są specyficzne dla `CView` klasy, [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) jest zawsze używana przed wykonaniem tych czynności.

Pasek podziału: kontrolka, która jest umieszczana między wierszami i kolumnami okienek. Może służyć do dostosowywania rozmiarów wierszy lub kolumn okienek.

Pole rozdzielacza: formant w dynamiczny `CSplitterWnd` , który służy do tworzenia nowych wierszy lub kolumn okienek. Znajduje się w górnej części pionowych pasków przewijania lub po lewej stronie poziomych pasków przewijania.

Część wspólna rozdzielacza: część wspólna pionowego paska podziału i poziomego paska podziału. Możesz przeciągnąć go, aby dopasować jednocześnie rozmiar wiersza i kolumny okienek.

## <a name="shared-scroll-bars"></a>Udostępnione paski przewijania

`CSplitterWnd`Klasa obsługuje również współużytkowane paski przewijania. Te kontrolki paska przewijania są elementami podrzędnymi `CSplitterWnd` i są współdzielone z różnymi okienkami w rozdzielaczu.

Na przykład w oknie 1 kolumny x 2 wiersza można określić WS_VSCROLL podczas tworzenia `CSplitterWnd` . System Windows tworzy specjalną kontrolkę paska przewijania, która jest współużytkowana przez dwa okienka.

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

Gdy użytkownik przesunie pasek przewijania, WM_VSCROLL komunikaty będą wysyłane do obu widoków. Gdy widok ustawi pozycję paska przewijania, zostanie ustawiony współużytkowany pasek przewijania.

Należy zauważyć, że udostępnione paski przewijania są najbardziej przydatne w przypadku podobnych obiektów widoku. Jeśli Mieszasz widoki różnych typów w rozdzielaczu, może być konieczne napisanie specjalnego kodu w celu skoordynowania ich pozycji przewijania. Każda `CView` Klasa pochodna korzystająca z `CWnd` interfejsów API paska przewijania zostanie oddelegowana na udostępniony pasek przewijania, jeśli istnieje. `CScrollView`Implementacja jest przykładem `CView` klasy, która obsługuje udostępnione paski przewijania. Klasy, które nie pochodzą od `CView` klas, które opierają się na paskach przewijania niekontrolujących lub klasy korzystające ze standardowych implementacji systemu Windows (na przykład `CEditView` ) nie będą działać z funkcją współużytkowanego paska przewijania `CSplitterWnd` .

## <a name="minimum-sizes"></a>Minimalne rozmiary

Dla każdego wiersza ma minimalną wysokość wiersza, a dla każdej kolumny istnieje minimalna szerokość kolumny. Ta minimalna gwarantuje, że okienko nie jest zbyt małe, aby można było je wyświetlić w pełnych szczegółach.

W przypadku statycznego okna rozdzielacza początkowa minimalna wysokość wiersza i szerokość kolumny wynosi 0. W przypadku dynamicznego okna rozdzielacza początkowa minimalna wysokość wiersza i szerokość kolumny są ustawiane przez parametr *sizeMin* `CSplitterWnd::Create` funkcji.

Te minimalne rozmiary można zmienić przy użyciu funkcji [CSplitterWnd:: SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) i [CSplitterWnd:: SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) .

## <a name="actual-vs-ideal-sizes"></a>Rzeczywiste i idealne rozmiary

Układ okienek w oknie rozdzielacza zależy od rozmiaru ramki, która je zawiera. Gdy użytkownik zmienia rozmiar ramki zawierającej, `CSplitterWnd` Zmienia położenie i zmienia rozmiar okienek, tak aby pasowały do nich, jak to możliwe.

Użytkownik może ręcznie ustawić wysokość wiersza i szerokość kolumny lub program może ustawić idealny rozmiar przy użyciu `CSplitterWnd` klasy. Rzeczywisty rozmiar może być mniejszy lub większy niż idealny. System Windows dostosowuje rzeczywisty rozmiar, jeśli nie ma wystarczająco dużo miejsca, aby wyświetlić idealny rozmiar lub gdy jest zbyt dużo puste miejsce w prawej lub dolnej części okna rozdzielacza.

## <a name="custom-controls"></a>Formanty niestandardowe

Możesz przesłonić wiele funkcji, aby zapewnić dostosowane zachowanie i dostosowany interfejs. Można zastąpić ten pierwszy zestaw, aby udostępnić alternatywne grafiki dla różnych składników graficznych okna rozdzielacza.

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

Ta funkcja jest wywoływana, aby utworzyć współdzieloną kontrolkę paska przewijania. Można zastąpić go, aby utworzyć dodatkowe kontrolki obok paska przewijania.

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

Te funkcje implementują logikę dynamicznego okna rozdzielacza. Można je zastąpić, aby zapewnić bardziej zaawansowaną logikę rozdzielacza.

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>Funkcja CView

`CView`Klasa używa następujących poleceń wysokiego poziomu, aby delegować do `CSplitterWnd` implementacji. Ponieważ te polecenia są wirtualne, standardowa `CView` implementacja nie będzie wymagała, `CSplitterWnd` aby cała implementacja była połączona. W przypadku aplikacji, które używają `CView` , ale nie `CSplitterWnd` , `CSplitterWnd` implementacja nie zostanie połączona z aplikacją.

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   Sprawdza, czy ID_NEXT_PANE lub ID_PREV_PANE jest obecnie możliwe.

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   Wykonuje polecenie "Następne okienko" lub "poprzednie okienko".

- `virtual BOOL DoKeyboardSplit();`

   Wykonuje polecenie podziału klawiatury, zwykle "podział okna".

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
