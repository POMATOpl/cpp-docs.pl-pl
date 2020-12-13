---
description: 'Dowiedz się więcej na temat: Przewodnik: umieszczanie formantów na paskach narzędzi'
title: 'Wskazówki: umieszczanie formantów na paskach narzędzi'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: eafb1afa2ffffeaaabfc6b463e2951d8d532db58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143055"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Wskazówki: umieszczanie formantów na paskach narzędzi

W tym artykule opisano, jak dodać przycisk paska narzędzi zawierający formant systemu Windows do paska narzędzi. W MFC, przycisk paska narzędzi musi być klasą pochodną [klasy CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md), na przykład Klasa [CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), Klasa [CMFCToolBarEditBoxButton](../mfc/reference/cmfctoolbareditboxbutton-class.md), Klasa [CMFCDropDownToolbarButton](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)lub [Klasa CMFCToolBarMenuButton](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Dodawanie kontrolek do pasków narzędzi

Aby dodać formant do paska narzędzi, wykonaj następujące kroki:

1. Zarezerwuj fikcyjny identyfikator zasobu dla przycisku w zasobie nadrzędnego paska narzędzi. Aby uzyskać więcej informacji o sposobach tworzenia przycisków przy użyciu **edytora pasków narzędzi** w programie Visual Studio, zobacz artykuł [Edytor paska narzędzi](../windows/toolbar-editor.md) .

1. Zarezerwuj obraz paska narzędzi (ikona przycisku) dla przycisku we wszystkich bitmapach nadrzędnego paska narzędzi.

1. W programie obsługi komunikatów, który przetwarza `AFX_WM_RESETTOOLBAR` komunikat, wykonaj następujące czynności:

   1. Utwórz kontrolkę Button przy użyciu `CMFCToolbarButton` klasy pochodnej.

   1. Zastąp przycisk fikcyjny nową kontrolką, korzystając z [CMFCToolBar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Można skonstruować obiekt Button na stosie, ponieważ `ReplaceButton` kopiuje obiekt Button i utrzymuje kopię.

> [!NOTE]
> Jeśli włączono Dostosowywanie w aplikacji, może być konieczne zresetowanie paska narzędzi przy użyciu przycisku **Resetuj** na karcie **paski narzędzi** okna dialogowego **Dostosowywanie** , aby wyświetlić zaktualizowaną kontrolkę w aplikacji po ponownym kompilacji. Stan paska narzędzi jest zapisywany w rejestrze systemu Windows, a informacje rejestru są ładowane i stosowane po `ReplaceButton` wykonaniu tej metody podczas uruchamiania aplikacji.

## <a name="toolbar-controls-and-customization"></a>Formanty i Dostosowywanie paska narzędzi

Karta **polecenia** okna dialogowego **Dostosowywanie** zawiera listę poleceń, które są dostępne w aplikacji. Domyślnie okno dialogowe **Dostosowywanie** przetwarza menu aplikacji i tworzy listę standardowych przycisków paska narzędzi w każdej kategorii menu. Aby zachować rozszerzone funkcje, które zapewnia formant Toolbar, należy zastąpić standardowy przycisk paska narzędzi formantem niestandardowym w oknie dialogowym **Dostosuj** .

Po włączeniu dostosowywania można utworzyć okno dialogowe **Dostosowywanie** w programie obsługi dostosowywania przy `OnViewCustomize` użyciu klasy [klasy CMFCToolBarsCustomizeDialog](../mfc/reference/cmfctoolbarscustomizedialog-class.md) . Przed wyświetleniem okna dialogowego **Dostosowywanie** przez wywołanie [CMFCToolBarsCustomizeDialog:: Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), Call [CMFCToolBarsCustomizeDialog:: ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) , aby zastąpić przycisk standardowy nową kontrolką.

## <a name="example-creating-a-find-combo-box"></a>Przykład: Tworzenie pola kombi Znajdź

W tej sekcji opisano sposób tworzenia kontrolki pola kombi **Znajdź** , która pojawia się na pasku narzędzi i zawiera ostatnio używane ciągi wyszukiwania. Użytkownik może wpisać ciąg w kontrolce, a następnie nacisnąć klawisz ENTER w celu przeszukania dokumentu lub nacisnąć klawisz Escape, aby zwrócić fokus do ramki głównej. W tym przykładzie przyjęto założenie, że dokument jest wyświetlany w widoku pochodnym [klasy elementu CEditView](../mfc/reference/ceditview-class.md).

### <a name="creating-the-find-control"></a>Tworzenie kontrolki Znajdź

Najpierw Utwórz formant pola kombi **wyszukiwania** :

1. Dodaj przycisk i jego polecenia do zasobów aplikacji:

   1. W obszarze zasoby aplikacji Dodaj nowy przycisk z `ID_EDIT_FIND` identyfikatorem polecenia do paska narzędzi w aplikacji i do wszystkich Bitmap skojarzonych z paskiem narzędzi.

   1. Utwórz nowy element menu z `ID_EDIT_FIND` identyfikatorem polecenia.

   1. Dodaj nowy ciąg "Znajdź text\nFind" do tabeli ciągów i przypisz mu `ID_EDIT_FIND_COMBO` Identyfikator polecenia. Ten identyfikator będzie używany jako identyfikator polecenia przycisku **wyszukiwania** pola kombi.

        > [!NOTE]
        > Ponieważ `ID_EDIT_FIND` jest to standardowe polecenie, które jest przetwarzane przez `CEditView` program, nie jest wymagane zaimplementowanie specjalnego programu obsługi dla tego polecenia.  Należy jednak zaimplementować procedurę obsługi dla nowego polecenia `ID_EDIT_FIND_COMBO` .

1. Utwórz nową klasę, która `CFindComboBox` pochodzi od [klasy CComboBox](../mfc/reference/ccombobox-class.md).

1. W `CFindComboBox` klasie Zastąp `PreTranslateMessage` metodę wirtualną. Ta metoda spowoduje włączenie pola kombi w celu przetworzenia komunikatu [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) . Jeśli użytkownik trafi klawisz Escape ( `VK_ESCAPE` ), zwróć fokus do okna głównej ramki. Jeśli użytkownik trafi klawisz ENTER ( `VK_ENTER` ), Opublikuj w oknie głównej ramki `WM_COMMAND` komunikat zawierający `ID_EDIT_FIND_COMBO` Identyfikator polecenia.

1. Utwórz klasę dla przycisku **Znajdź** pole kombi pochodnego od [klasy CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). W tym przykładzie nazywa się `CFindComboButton` .

1. Konstruktor `CMFCToolbarComboBoxButton` przyjmuje trzy parametry: Identyfikator polecenia przycisku, indeks obrazu przycisku i styl pola kombi. Ustaw następujące parametry:

   1. Przekaż `ID_EDIT_FIND_COMBO` jako identyfikator polecenia.

   1. Użyj [CCommandManager:: GetCmdImage](reference/internal-classes.md) z, `ID_EDIT_FIND` Aby pobrać indeks obrazu.

   1. Aby uzyskać listę dostępnych stylów pól kombi, zobacz [Style pola kombi](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. W `CFindComboButton` klasie Zastąp `CMFCToolbarComboBoxButton::CreateCombo` metodę. W tym miejscu należy utworzyć `CFindComboButton` obiekt i zwrócić do niego wskaźnik.

1. Użyj makra [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) , aby przycisk kombi był trwały. Menedżer obszarów roboczych automatycznie ładuje i zapisuje stan przycisku w rejestrze systemu Windows.

1. Zaimplementuj `ID_EDIT_FIND_COMBO` procedurę obsługi w widoku dokumentu. Użyj [CMFCToolBar:: GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) with `ID_EDIT_FIND_COMBO` , aby pobrać wszystkie przyciski pola kombi **wyszukiwania** . Istnieje kilka kopii przycisku z tym samym IDENTYFIKATORem polecenia z powodu dostosowania.

1. W programie `ID_EDIT_FIND` obsługi komunikatów `OnFind` Użyj [CMFCToolBar:: IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) , aby określić, czy polecenie Find zostało wysłane z pola kombi **Znajdź** . Jeśli tak, Znajdź tekst i Dodaj ciąg wyszukiwania do pola kombi.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Dodawanie formantu Find do głównego paska narzędzi

Aby dodać przycisk pola kombi do paska narzędzi, wykonaj następujące kroki:

1. Zaimplementuj `AFX_WM_RESETTOOLBAR` procedurę obsługi komunikatów `OnToolbarReset` w oknie głównym ramki.

    > [!NOTE]
    > Struktura wysyła ten komunikat do okna głównej ramki, gdy zostanie zainicjowany pasek narzędzi podczas uruchamiania aplikacji, lub gdy pasek narzędzi zostanie zresetowany podczas dostosowywania. W obu przypadkach należy zamienić standardowy przycisk paska narzędzi na przycisk pola kombi **Wyszukiwanie** niestandardowe.

1. W programie `AFX_WM_RESETTOOLBAR` obsługi Przejrzyj identyfikator paska narzędzi, czyli *WPARAM* komunikatu AFX_WM_RESETTOOLBAR. Jeśli identyfikator paska narzędzi jest równy rozmiarowi paska narzędzi zawierającego przycisk **Znajdź** pole kombi, wywołaj [CMFCToolBar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) , aby zastąpić przycisk **Znajdź** (czyli przycisk z identyfikatorem polecenia `ID_EDIT_FIND)` z `CFindComboButton` obiektem.

    > [!NOTE]
    > Można skonstruować `CFindComboBox` obiekt na stosie, ponieważ kopiuje on `ReplaceButton` obiekt Button i utrzymuje kopię.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Dodawanie kontrolki Znajdź do okna dialogowego Dostosowywanie

W procedurze obsługi dostosowywania `OnViewCustomize` Wywołaj [CMFCToolBarsCustomizeDialog:: ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) , aby zastąpić przycisk **Znajdź** (czyli przycisk z identyfikatorem polecenia `ID_EDIT_FIND` ) `CFindComboButton` obiektem.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../mfc/hierarchy-chart.md)<br/>
[Klasy](../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCToolBar](../mfc/reference/cmfctoolbar-class.md)<br/>
[Klasa CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Klasa CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Klasa CMFCToolBarsCustomizeDialog](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
