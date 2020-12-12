---
description: 'Dowiedz się więcej na temat: Dodawanie strony właściwości (samouczek ATL, część 6)'
title: Dodawanie strony właściwości (ALT — Samouczek, część 6)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
ms.openlocfilehash: c33789919e104cc1600622dc3972a23069afe573
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166292"
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>Dodawanie strony właściwości (ALT — Samouczek, część 6)

> [!NOTE]
> Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

Strony właściwości są implementowane jako oddzielne obiekty COM, które umożliwiają udostępnianie ich w razie potrzeby. W tym kroku wykonasz następujące zadania, aby dodać stronę właściwości do kontrolki:

- Tworzenie zasobu strony właściwości

- Dodawanie kodu do tworzenia strony właściwości i zarządzania nią

- Dodawanie strony właściwości do kontrolki

## <a name="creating-the-property-page-resource"></a>Tworzenie zasobu strony właściwości

Aby dodać stronę właściwości do kontrolki, użyj szablonu strony właściwości ATL.

### <a name="to-add-a-property-page"></a>Aby dodać stronę właściwości

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy `Polygon` .

1. W menu skrótów kliknij polecenie **Dodaj**  >  **nowy element**.

1. Z listy **szablonów wybierz opcję**  >  **Strona właściwości ATL ATL** , a następnie kliknij przycisk **Dodaj**.

1. Gdy zostanie wyświetlony **Kreator strony właściwości ATL** , wprowadź wartość *prop* jako **krótką** nazwę.

1. Kliknij pozycję **ciągi** , aby otworzyć stronę **ciągi** i wprowadź **&Wielokąt** jako **tytuł**.

   **Tytuł** strony właściwości jest ciągiem, który pojawia się na karcie dla tej strony. **Ciąg doc** to opis, którego ramka właściwości używa do umieszczenia w wierszu stanu lub etykietce narzędzia. Należy zauważyć, że standardowa ramka właściwości nie korzysta obecnie z tego ciągu, więc można pozostawić ją wartością domyślną. W tej chwili nie zostanie wygenerowany **plik pomocy** , dlatego Usuń wpis w tym polu tekstowym.

1. Kliknij przycisk **Zakończ**, a obiekt strony właściwości zostanie utworzony.

Tworzone są następujące trzy pliki:

|Plik|Opis|
|----------|-----------------|
|Prop. h|Zawiera klasę języka C++ `CPolyProp` , która implementuje stronę właściwości.|
|Z właściwością. cpp|Zawiera plik. h.|
|RGS.|Skrypt rejestru, który rejestruje obiekt strony właściwości.|

Wprowadzono również następujące zmiany kodu:

- Nowa strona właściwości zostanie dodana do mapy wpisów obiektów w wielokąta. cpp.

- `PolyProp`Klasa jest dodawana do wielokąta pliku IDL.

- Nowy plik skryptu rejestru DBPROP. RGS jest dodawany do zasobu projektu.

- Szablon okna dialogowego jest dodawany do zasobu projektu dla strony właściwości.

- Określone ciągi właściwości są dodawane do tabeli ciągów zasobów.

Teraz Dodaj pola, które mają być wyświetlane na stronie właściwości.

### <a name="to-add-fields-to-the-property-page"></a>Aby dodać pola do strony właściwości

1. W **Eksplorator rozwiązań** kliknij dwukrotnie plik zasobów wielokąt. rc. Spowoduje to otwarcie **Widok zasobów**.

1. W **Widok zasobów** rozwiń `Dialog` węzeł i kliknij dwukrotnie `IDD_POLYPROP` . Należy zauważyć, że wyświetlane okno dialogowe jest puste, z wyjątkiem etykiety, która informuje o wstawieniu kontrolek w tym miejscu.

1. Zaznacz tę etykietę i zmień ją na odczytaną, zmieniając `Sides:` tekst **podpisu** w oknie **Właściwości** .

1. Zmień rozmiar pola etykiety, tak aby pasował do rozmiaru tekstu.

1. Przeciągnij **kontrolkę Edycja** z **przybornika** z prawej strony etykiety.

1. Na koniec Zmień **Identyfikator** kontrolki edycji na `IDC_SIDES` za pomocą okna **Właściwości** .

Spowoduje to zakończenie procesu tworzenia zasobu strony właściwości.

## <a name="adding-code-to-create-and-manage-the-property-page"></a>Dodawanie kodu do tworzenia strony właściwości i zarządzania nią

Po utworzeniu zasobu strony właściwości należy napisać kod implementacji.

Najpierw włącz klasę, `CPolyProp` Aby ustawić liczbę boków w obiekcie po naciśnięciu przycisku **Zastosuj** .

### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>Aby zmodyfikować funkcję Zastosuj, aby ustawić liczbę boków

1. Zastąp `Apply` funkcję w funkcji unprop. h następującym kodem:

    [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]

Na stronie właściwości może być dołączonych więcej niż jeden klient, więc `Apply` Funkcja pętle i wywołań `put_Sides` na każdym kliencie z wartością pobieraną z pola edycji. Używasz klasy [CComQIPtr](../atl/reference/ccomqiptr-class.md) , która wykonuje `QueryInterface` na każdym obiekcie, aby uzyskać `IPolyCtl` interfejs z `IUnknown` interfejsu (przechowywanego w `m_ppUnk` tablicy).

Kod sprawdza teraz, czy `Sides` Właściwość rzeczywiście pracowała. Jeśli to się nie powiedzie, kod wyświetli okno komunikatu z informacjami o błędzie z `IErrorInfo` interfejsu. Zazwyczaj kontener żąda obiektu dla `ISupportErrorInfo` interfejsu i wywołań `InterfaceSupportsErrorInfo` najpierw, aby określić, czy obiekt obsługuje ustawianie informacji o błędach. Możesz pominąć to zadanie.

[CComPtr](../atl/reference/ccomptr-class.md) pomaga automatycznie obsłużyć zliczanie odwołań, więc nie trzeba wywoływać `Release` interfejsu. `CComBSTR` pomaga w przetwarzaniu BSTR, dlatego nie trzeba wykonywać końcowego `SysFreeString` wywołania. Należy również użyć jednej z różnych klas konwersji ciągów, aby w razie potrzeby można było skonwertować wartość BSTR (dlatego USES_CONVERSION makro jest na początku funkcji).

Należy także ustawić flagę Dirty strony właściwości, aby wskazać, że przycisk **Zastosuj** powinien być włączony. Dzieje się tak, gdy użytkownik zmieni wartość w polu Edytuj **strony** .

### <a name="to-handle-the-apply-button"></a>Aby obsłużyć przycisk Zastosuj

1. W **Widok klasy** kliknij prawym przyciskiem myszy `CPolyProp` i kliknij pozycję **Właściwości** w menu skrótów.

1. W oknie **Właściwości** kliknij ikonę **zdarzenia** .

1. Rozwiń `IDC_SIDES` węzeł na liście zdarzeń.

1. Wybierz `EN_CHANGE` i z menu rozwijanego po prawej stronie kliknij pozycję **\<Add> OnEnChangeSides**. `OnEnChangeSides`Deklaracja procedury obsługi zostanie dodana do funkcji unprop. h i implementacji procedury obsługi do funkcji unprop. cpp.

Następnie zmodyfikujesz procedurę obsługi.

### <a name="to-modify-the-onenchangesides-method"></a>Aby zmodyfikować metodę OnEnChangeSides

1. Dodaj następujący kod w metodzie unprop. cpp do `OnEnChangeSides` metody (usuwanie dowolnego kodu, który zawiera Kreator):

    [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]

`OnEnChangeSides` zostanie wywołana, gdy zostanie `WM_COMMAND` wysłany komunikat z `EN_CHANGE` powiadomieniem dla `IDC_SIDES` kontrolki. `OnEnChangeSides` następnie wywołuje `SetDirty` i przekazuje wartość true, aby wskazać, że strona właściwości jest teraz zanieczyszczony i przycisk **Zastosuj** powinien być włączony.

## <a name="adding-the-property-page-to-the-control"></a>Dodawanie strony właściwości do kontrolki

Szablon i Kreator strony właściwości ATL nie automatycznie dodają strony właściwości do kontrolki, ponieważ w projekcie może istnieć wiele kontrolek. Musisz dodać wpis do mapy właściwości kontrolki.

### <a name="to-add-the-property-page"></a>Aby dodać stronę właściwości

1. Otwórz PolyCtl. h i Dodaj te wiersze do mapy właściwości:

    [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]

Mapa właściwości kontrolki wygląda teraz następująco:

[!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]

Można dodać `PROP_PAGE` makro z identyfikatorem CLSID strony właściwości, ale jeśli używasz `PROP_ENTRY` makra jak pokazano, `Sides` wartość właściwości jest również zapisywana, gdy formant zostanie zapisany.

Trzy parametry do makra to opis właściwości, identyfikator DISPID właściwości i CLSID strony właściwości, która zawiera właściwość. Jest to przydatne, jeśli na przykład załadujesz formant do Visual Basic i ustawisz liczbę boków w czasie projektowania. Ponieważ liczba boków jest zapisywana, po ponownym załadowaniu projektu Visual Basic liczba stron zostanie przywrócona.

## <a name="building-and-testing-the-control"></a>Kompilowanie i testowanie kontrolki

Teraz Kompiluj tę kontrolkę i Wstaw ją do kontenera testów kontrolki ActiveX. W **kontenerze Test**, w menu **Edycja** kliknij polecenie **obiekt klasy PolyCtl**. Zostanie wyświetlona strona właściwości zawierająca informacje, które zostały dodane.

Przycisk **Zastosuj** jest początkowo wyłączony. Zacznij wpisywać wartość w polu **boki** , a przycisk **Zastosuj** zostanie włączony. Po wprowadzeniu wartości kliknij przycisk **Zastosuj** . Kontrolka wyświetli zmiany i przycisk **Zastosuj** zostanie ponownie wyłączona. Spróbuj wprowadzić nieprawidłową wartość. Zostanie wyświetlone okno komunikatu zawierające opis błędu, który został ustawiony z `put_Sides` funkcji.

Następnie umieścisz swój formant na stronie sieci Web.

[Wróć do kroku 5](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [w kroku 7](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)

## <a name="see-also"></a>Zobacz też

[Samouczek](../atl/active-template-library-atl-tutorial.md)
