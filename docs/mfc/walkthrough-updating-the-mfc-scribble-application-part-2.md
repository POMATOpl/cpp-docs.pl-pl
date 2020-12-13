---
description: 'Dowiedz się więcej na temat: Przewodnik: aktualizowanie aplikacji bazgrołów MFC (część 2)'
title: 'Wskazówki: aktualizowanie aplikacji bazgrołów MFC (część 2)'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: 2520ac8fc1c66a2fc388738d22f4851547b6d03b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142964"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>Wskazówki: aktualizowanie aplikacji bazgrołów MFC (część 2)

W [części 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) tego instruktażu pokazano, jak dodać wstążkę pakietu Office Fluent do klasycznej aplikacji bazgroł. Ta część pokazuje, jak dodać panele wstążki i kontrolki, których użytkownicy mogą używać zamiast menu i poleceń.

## <a name="prerequisites"></a>Wymagania wstępne

[Przykłady Visual C++](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a> Poszczególne

Ta część przewodnika zawiera następujące sekcje:

- [Dodawanie nowych paneli do wstążki](#addnewpanel)

- [Dodawanie panelu pomocy do wstążki](#addhelppanel)

- [Dodawanie panelu pióra do wstążki](#addpenpanel)

- [Dodawanie przycisku koloru do wstążki](#addcolorbutton)

- [Dodawanie elementu członkowskiego koloru do klasy dokumentu](#addcolormember)

- [Inicjowanie piór i preferencje zapisywania](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a> Dodawanie nowych paneli do wstążki

W tych krokach pokazano, jak dodać Panel **widoku** zawierający dwa pola wyboru kontrolujące widoczność paska narzędzi i pasek stanu, a także panel **okna** zawierający przycisk podziału zorientowanego pionowo, który kontroluje tworzenie i rozmieszczenie okien interfejsu wielu dokumentów (MDI).

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Aby dodać Panel wyświetlania i panel okna do paska wstążki

1. Utwórz panel o nazwie `View` , który ma dwa pola wyboru, które przełączają pasek stanu i pasek narzędzi.

   1. Z **przybornika** przeciągnij **panel** do kategorii **Home** . Następnie przeciągnij dwa **pola wyboru** do panelu.

   1. Kliknij panel, aby zmodyfikować jego właściwości. Zmień **napis** na `View` .

   1. Kliknij pierwsze pole wyboru, aby zmodyfikować jego właściwości. Zmień **Identyfikator** na `ID_VIEW_TOOLBAR` i **podpis** na `Toolbar` .

   1. Kliknij drugie pole wyboru, aby zmodyfikować jego właściwości. Zmień **Identyfikator** na `ID_VIEW_STATUS_BAR` i **podpis** na `Status Bar` .

1. Utwórz panel o nazwie `Window` , który ma przycisk podziału. Gdy użytkownik kliknie przycisk podziału, menu skrótów wyświetli trzy polecenia, które są już zdefiniowane w aplikacji Bazgroły.

   1. Z **przybornika** przeciągnij **panel** do kategorii **Home** . Następnie przeciągnij **przycisk** do panelu.

   1. Kliknij panel, aby zmodyfikować jego właściwości. Zmień **napis** na `Window` .

   1. Kliknij przycisk. Zmień pozycję **Caption** na `Windows` , **klawisze** do `w` , **duży indeks obrazu** na `1` i **Tryb podziału** na `False` . Następnie kliknij przycisk wielokropka (**...**) obok **pozycji menu** , aby otworzyć okno dialogowe **Edytor elementów** .

   1. Kliknij przycisk **Dodaj** trzy razy, aby dodać trzy przyciski.

   1. Kliknij pierwszy przycisk, a następnie zmień **napis** na `New Window` i **Identyfikator** na `ID_WINDOW_NEW` .

   1. Kliknij drugi przycisk, a następnie zmień **napis** na `Cascade` i **Identyfikator** na `ID_WINDOW_CASCADE` .

   1. Kliknij trzeci przycisk, a następnie zmień **napis** na `Tile` i **Identyfikator** na `ID_WINDOW_TILE_HORZ` .

1. Zapisz zmiany, a następnie Skompiluj i uruchom aplikację. Należy wyświetlić panele **Widok** i **okno** . Kliknij przyciski, aby potwierdzić, że działają poprawnie.

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a> Dodawanie panelu pomocy do wstążki

Teraz można przypisać dwa elementy menu, które są zdefiniowane w aplikacji Bazgroły, do przycisków wstążki o nazwach **tematów pomocy** i **bazgrołów**. Przyciski są dodawane do nowego panelu o nazwie **help**.

### <a name="to-add-a-help-panel"></a>Aby dodać Panel pomocy

1. Z **przybornika** przeciągnij **panel** do kategorii **Home** . Następnie przeciągnij dwa **przyciski** do panelu.

1. Kliknij panel, aby zmodyfikować jego właściwości. Zmień **napis** na `Help` .

1. Kliknij przycisk pierwszy. Zmień **napis** na `Help Topics` i **Identyfikator** na `ID_HELP_FINDER` .

1. Kliknij drugi przycisk. Zmień **napis** na `About Scribble...` i **Identyfikator** na `ID_APP_ABOUT` .

1. Zapisz zmiany, a następnie Skompiluj i uruchom aplikację. Powinien zostać wyświetlony panel **pomocy** , który zawiera dwa przyciski wstążki.

   > [!IMPORTANT]
   > Po kliknięciu przycisku **Tematy pomocy** aplikacja bazgroł otwiera skompresowany plik pomocy HTML (. chm) o nazwie *your_project_name*. chm. W związku z tym, jeśli projekt nie ma nazwy bazgrołów, należy zmienić nazwę pliku pomocy na nazwę projektu.

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a> Dodawanie panelu pióra do wstążki

Teraz Dodaj panel, aby wyświetlić przyciski, które kontrolują grubość i kolor pióra. Ten panel zawiera pole wyboru, które powoduje przełączenie między piórem grubym i cienkim. Jego funkcja jest podobna do pozycji menu **gruby wiersz** w aplikacji Bazgroły.

Oryginalna aplikacja bazgrołów umożliwia użytkownikowi wybranie szerokości pióra z okna dialogowego, które pojawia się, gdy użytkownik kliknie ikonę **pióra** w menu. Ponieważ pasek wstążki ma wystarczającą ilość miejsca na nowe kontrolki, można zamienić okno dialogowe, używając dwóch pól kombi na Wstążce. Jedno pole kombi dostosowuje szerokość cienkiego pióra, a inne pole kombi dostosowuje szerokość grubego pióra.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Aby dodać Panel pióra i pola kombi do wstążki

1. Z **przybornika** przeciągnij **panel** do kategorii **Home** . Następnie przeciągnij **pole wyboru** i dwa **pola kombi** do panelu.

1. Kliknij panel, aby zmodyfikować jego właściwości. Zmień **napis** na `Pen` .

1. Kliknij pole wyboru. Zmień **napis** na `Use Thick` i **Identyfikator** na `ID_PEN_THICK_OR_THIN` .

1. Kliknij pierwsze pole kombi. Zmień **napis** na `Thin Pen` , **Identyfikator** na `ID_PEN_THIN_WIDTH` , **wpisz** do `Drop List` , **dane** do `1;2;3;4;5;6;7;8;9;` i **tekst** do `2` .

1. Kliknij drugie pole kombi. Zmień **napis** na `Thick Pen` , **Identyfikator** na `ID_PEN_THICK_WIDTH` , **wpisz** do `Drop List` , **dane** do `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;` i **tekst** do `5` .

1. Nowe pola kombi nie odpowiadają żadnym istniejącym elementom menu, dlatego należy utworzyć element menu dla każdej opcji pióra.

   1. W oknie **Widok zasobów** Otwórz zasób menu **IDR_SCRIBBTYPE** .

   1. Kliknij pozycję **pióro** , aby otworzyć menu pióro. Następnie kliknij **Wpisz tutaj** i wpisz `Thi&n Pen` .

   1. Kliknij prawym przyciskiem myszy wprowadzony tekst, aby otworzyć okno **Właściwości** , a następnie zmień właściwość ID na `ID_PEN_THIN_WIDTH` .

   1. Utwórz procedurę obsługi zdarzeń dla każdego elementu menu pióra. Kliknij prawym przyciskiem myszy element menu **pióro Thi&n** , który został utworzony, a następnie kliknij polecenie **Dodaj obsługę zdarzeń**. Zostanie wyświetlony **Kreator obsługi zdarzeń** .

   1. W oknie **Lista klas** w kreatorze wybierz pozycję **CScribbleDoc** , a następnie kliknij pozycję **Dodaj i edytuj**. Polecenie tworzy program obsługi zdarzeń o nazwie `CScribbleDoc::OnPenThinWidth` .

   1. Dodaj następujący kod do `CScribbleDoc::OnPenThinWidth` .

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Następnie Utwórz element menu i obsługę zdarzeń dla Grubego pióra.

   1. W oknie **Widok zasobów** Otwórz zasób menu **IDR_SCRIBBTYPE** .

   1. Kliknij pozycję **pióro** , aby otworzyć menu pióro. Następnie kliknij **Wpisz tutaj** i wpisz `Thic&k Pen` .

   1. Kliknij prawym przyciskiem myszy wprowadzony tekst, aby wyświetlić okno **Właściwości** . Zmień Właściwość ID na `ID_PEN_THICK_WIDTH` .

   1. Kliknij prawym przyciskiem myszy **gruby element menu pióra** , który został utworzony, a następnie kliknij polecenie **Dodaj obsługę zdarzeń**. Zostanie wyświetlony **Kreator obsługi zdarzeń** .

   1. W oknie **Lista klas** kreatora wybierz pozycję **CScribbleDoc** , a następnie kliknij pozycję **Dodaj i edytuj**. Polecenie tworzy program obsługi zdarzeń o nazwie `CScribbleDoc::OnPenThickWidth` .

   1. Dodaj następujący kod do `CScribbleDoc::OnPenThickWidth` .

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Zapisz zmiany, a następnie Skompiluj i uruchom aplikację. Powinny być wyświetlane nowe przyciski i pola kombi. Spróbuj użyć różnych szerokości pióra do bazgrołów.

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a> Dodawanie przycisku koloru do panelu pióra

Następnie Dodaj obiekt [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) , który umożliwia użytkownikowi bazgrołę.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Aby dodać przycisk koloru do panelu pióra

1. Zanim dodasz przycisk Color, Utwórz dla niego element menu. W oknie **Widok zasobów** Otwórz zasób menu **IDR_SCRIBBTYPE** . Kliknij element menu **pióra** , aby otworzyć menu pióro. Następnie kliknij **Wpisz tutaj** i wpisz `&Color` . Kliknij prawym przyciskiem myszy wprowadzony tekst, aby wyświetlić okno **Właściwości** . Zmień identyfikator na `ID_PEN_COLOR` .

1. Teraz Dodaj przycisk Color (kolor). Z **przybornika** przeciągnij **przycisk koloru** do panelu **pióra** .

1. Kliknij przycisk Color (kolor). Zmień **napis** na `Color` , **Identyfikator** na `ID_PEN_COLOR` , **prosty wygląd** `True` , **indeks dużego obrazu** do `1` i **Tryb podziału** na `False` .

1. Zapisz zmiany, a następnie Skompiluj i uruchom aplikację. Przycisk Nowy kolor powinien być wyświetlany w panelu **pióro** . Jednak nie można go użyć, ponieważ nie ma jeszcze obsługi zdarzeń. W następnych krokach pokazano, jak dodać program obsługi zdarzeń dla przycisku kolor.

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a> Dodawanie elementu członkowskiego koloru do klasy dokumentu

Ponieważ oryginalna aplikacja bazgrołów nie ma piór kolorowych, należy napisać dla nich implementację. Aby zapisać kolor pióra dokumentu, Dodaj nowy element członkowski do klasy dokumentu `CscribbleDoc` .

### <a name="to-add-a-color-member-to-the-document-class"></a>Aby dodać składową koloru do klasy dokumentu

1. W scribdoc. h, w `CScribbleDoc` klasie, Znajdź `// Attributes` sekcję. Dodaj następujące wiersze kodu po definicji `m_nThickWidth` elementu członkowskiego danych.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. Każdy dokument zawiera listę Stokes, które zostały już narysowane przez użytkownika. Każdy obrys jest definiowany przez `CStroke` obiekt. `CStroke`Klasa nie zawiera informacji o kolorze pióra, dlatego należy zmodyfikować klasę. W scribdoc. h w `CStroke` klasie Dodaj następujące wiersze kodu po definicji `m_nPenWidth` elementu członkowskiego danych.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. W scribdoc. h Dodaj nowy Konstruktor, `CStroke` którego parametry określają szerokość i kolor. Dodaj następujący wiersz kodu po `CStroke(UINT nPenWidth);` instrukcji.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. W scribdoc. cpp Dodaj implementację nowego `CStroke` konstruktora. Dodaj następujący kod po implementacji `CStroke::CStroke(UINT nPenWidth)` konstruktora.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. Zmień drugi wiersz `CStroke::DrawStroke` metody w następujący sposób.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. Ustaw domyślny kolor pióra dla klasy dokumentu. W scribdoc. cpp Dodaj następujące wiersze do `CScribbleDoc::InitDocument` , po `m_nThickWidth = 5;` instrukcji.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. W scribdoc. cpp Zmień pierwszy wiersz `CScribbleDoc::NewStroke` metody na poniżej.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. Zmień ostatni wiersz `CScribbleDoc::ReplacePen` metody na następujący.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. Dodano `m_penColor` element członkowski w poprzednim kroku. Teraz Utwórz procedurę obsługi zdarzeń dla przycisku Color, który ustawia element członkowski.

   1. W oknie **Widok zasobów** Otwórz zasób menu IDR_SCRIBBTYPE.

   1. Kliknij prawym przyciskiem myszy element menu **kolor** , a następnie kliknij polecenie **Dodaj obsługę zdarzeń**. Zostanie wyświetlony **Kreator obsługi zdarzeń** .

   1. W oknie **Lista klas** w kreatorze wybierz pozycję **CScribbleDoc** , a następnie kliknij przycisk **Dodaj i edytuj** . Polecenie tworzy procedurę tworzenia `CScribbleDoc::OnPenColor` zdarzeń.

1. Zastąp tekst zastępczy dla `CScribbleDoc::OnPenColor` programu obsługi zdarzeń następującym kodem.

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. Zapisz zmiany, a następnie Skompiluj i uruchom aplikację. Teraz możesz nacisnąć przycisk Color (kolor) i zmienić kolor pióra.

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a> Inicjowanie piór i preferencje zapisywania

Następnie zainicjuj kolor i szerokość piór. Na koniec Zapisz i Załaduj kolor rysowania z pliku.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Aby zainicjować kontrolki na pasku wstążki

1. Zainicjuj pióra na pasku wstążki.

   Dodaj następujący kod do scribdoc. cpp, w `CScribbleDoc::InitDocument` metodzie, po `m_sizeDoc = CSize(200,200)` instrukcji.

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. Zapisz kolor rysowanie do pliku. Dodaj następującą instrukcję do scribdoc. cpp, w `CStroke::Serialize` metodzie, po `ar << (WORD)m_nPenWidth;` instrukcji.

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. Na koniec Załaduj kolor rysowania z pliku. Dodaj następujący wiersz kodu, w `CStroke::Serialize` metodzie, po `m_nPenWidth = w;` instrukcji.

   ```cpp
   ar >> m_penColor;
   ```

1. Teraz Bazgroły w kolorze i zapisujesz rysunek do pliku.

## <a name="conclusion"></a>Wniosek

Zaktualizowano aplikację bazgrołów MFC. Użyj tego przewodnika jako przewodnika po zmodyfikowaniu istniejących aplikacji.

## <a name="see-also"></a>Zobacz też

[Wskazówki](../mfc/walkthroughs-mfc.md)<br/>
[Przewodnik: aktualizowanie aplikacji bazgrołów MFC (część 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
