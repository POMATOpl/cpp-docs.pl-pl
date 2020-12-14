---
description: 'Dowiedz się więcej na temat: TN014: formanty niestandardowe'
title: 'TN014: formanty niestandardowe'
ms.date: 06/28/2018
f1_keywords:
- vc.controls
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
ms.openlocfilehash: c9b069e0101b279558c5bcd4ffb7f457120e8187
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215979"
---
# <a name="tn014-custom-controls"></a>TN014: formanty niestandardowe

Ta Uwaga opisuje obsługę MFC dla kontrolek niestandardowych i samorysowania. Opisuje ona również dynamiczną podklasę i opisuje relację między obiektami [CWnd](../mfc/reference/cwnd-class.md) a `HWND` s.

Przykładowa aplikacja MFC CTRLTEST ilustruje, jak używać wielu niestandardowych kontrolek. Zobacz kod źródłowy dla ogólnej przykładowej [CTRLTEST](../overview/visual-cpp-samples.md) i pomocy online dla MFC.

## <a name="owner-draw-controlsmenus"></a>Owner-Draw kontrolki/menu

System Windows zapewnia obsługę formantów i menu rysowania przez właściciela przy użyciu komunikatów systemu Windows. Okno nadrzędne dowolnego formantu lub menu odbiera te komunikaty i wywołuje funkcje w odpowiedzi. Można przesłonić te funkcje, aby dostosować wygląd i zachowanie wizualizacji lub menu rysowania przez właściciela.

MFC bezpośrednio obsługuje rysowanie przez właściciela przy użyciu następujących funkcji:

- [CWnd:: OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd:: OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd:: OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd:: OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

Można zastąpić te funkcje w `CWnd` klasie pochodnej, aby zaimplementować niestandardowe zachowanie rysowania.

To podejście nie prowadzi do ponownego użycia kodu. Jeśli masz dwie podobne kontrolki w dwóch różnych `CWnd` klasach, musisz zaimplementować zachowanie kontrolki niestandardowej w dwóch lokalizacjach. Architektura kontroli samorysowania obsługiwana przez MFC rozwiązuje ten problem.

## <a name="self-draw-controls-and-menus"></a>Self-Draw kontrolki i menu

MFC oferuje domyślną implementację (w `CWnd` klasach i [CMenu](../mfc/reference/cmenu-class.md) ) dla standardowych komunikatów rysowania przez właściciela. Ta domyślna implementacja spowoduje zdekodowanie parametrów rysowania przez właściciela i delegowanie komunikatów rysowania przez właściciela do kontrolek lub menu. Jest to nazywane samorysowaniem, ponieważ kod rysowania znajduje się w klasie kontrolki lub menu, a nie w oknie właściciela.

Za pomocą kontrolek samorysowania można tworzyć klasy kontroli wielokrotnego użytku, które używają semantyki rysowania przez właściciela, aby wyświetlić formant. Kod do rysowania kontrolki znajduje się w klasie kontrolki, a nie w jej obiekcie nadrzędnym. Jest to podejście zorientowane obiektowo do programowania formantów niestandardowych. Dodaj następującą listę funkcji do swoich klas samorysowania:

- Dla przycisków samorysowania:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- W przypadku menu z własnym rysowaniem:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- Dla pól listy z własnym rysowaniem:

    ```cpp
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this list box
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this list box

    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this list box if LBS_SORT
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this list box
    ```

- Dla samorysowania pól kombi:

    ```cpp
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this combo box
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this combo box

    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this combo box if CBS_SORT
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this combo box
    ```

Aby uzyskać szczegółowe informacje na temat struktur rysowania przez właściciela ([DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct), [MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct), [COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct)i [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct)), zobacz dokumentację MFC `CWnd::OnDrawItem` odpowiednio dla,, `CWnd::OnMeasureItem` `CWnd::OnCompareItem` i `CWnd::OnDeleteItem` .

## <a name="using-self-draw-controls-and-menus"></a>Używanie kontrolek i menu z własnym rysowaniem

W przypadku menu samorysowania należy zastępować `OnMeasureItem` `OnDrawItem` metody i.

W przypadku samorysowania pól listy i pól kombi należy przesłonić `OnMeasureItem` i `OnDrawItem` . Należy określić styl LBS_OWNERDRAWVARIABLE dla pól listy lub styl CBS_OWNERDRAWVARIABLE dla pól kombi w szablonie okna dialogowego. Styl OWNERDRAWFIXED nie będzie działał z elementami samorysowania, ponieważ stała wysokość elementu jest określana przed dołączeniem do pola listy formantów samorysowania. (Można użyć metod [CListBox:: SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) i [CComboBox:: SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) do pokonania tego ograniczenia).

Przełączenie do stylu OWNERDRAWVARIABLE spowoduje wymuszenie zastosowania przez system stylu NOINTEGRALHEIGHT do kontrolki. Ponieważ kontrolka nie może obliczyć wysokości całkowitej z elementami o zmiennym rozmiarze, domyślny styl INTEGRALHEIGHT jest ignorowany, a formant jest zawsze NOINTEGRALHEIGHT. Jeśli elementy mają stałą wysokość, można zapobiec narysowaniu częściowych elementów przez określenie rozmiaru formantu jako mnożnika liczby całkowitej rozmiaru elementu.

W przypadku samorysowania pól listy i pól kombi z stylem LBS_SORT lub CBS_SORT należy zastąpić `OnCompareItem` metodę.

Dla samorysowania pól listy i pól kombi `OnDeleteItem` nie są zwykle zastępowane. Można przesłonić, `OnDeleteItem` Jeśli chcesz wykonać jakiekolwiek specjalne przetwarzanie. Jeden przypadek, w którym będzie to miało zastosowanie, ma miejsce, gdy dodatkowa pamięć lub inne zasoby są przechowywane przy użyciu każdego pola listy lub elementu pola kombi.

## <a name="examples-of-self-drawing-controls-and-menus"></a>Przykłady formantów i menu Self-Drawing

Ogólna Przykładowa [CTRLTEST](../overview/visual-cpp-samples.md) MFC zawiera przykłady menu i samodzielnego rysowania.

Najbardziej typowym przykładem przycisku z własnym rysowaniem jest przycisk mapy bitowej. Przycisk mapy bitowej to przycisk, który pokazuje jeden, dwa lub trzy obrazy mapy bitowej dla różnych stanów. Przykładem tego jest podano w klasie MFC [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).

## <a name="dynamic-subclassing"></a>Dynamiczne podklasa

Czasami trzeba zmienić funkcjonalność obiektu, który już istnieje. Poprzednie przykłady wymagały dostosowania formantów przed ich utworzeniem. Dynamiczna podklasa umożliwia dostosowanie kontrolki, która została już utworzona.

Podklasa to termin systemu Windows służący do zastępowania <xref:System.Windows.Forms.Control.WndProc%2A> okna z dostosowaną `WndProc` i wywołującą starą `WndProc` funkcję domyślną.

Nie należy mylić tego kodu z klasą pochodną języka C++. Aby uzyskać wyjaśnienie, *Klasa bazowa* języka C++ i *Klasa pochodna* są analogiczne do *superklasy* i *podklas* w modelu obiektów systemu Windows. Tworzenie kodu języka C++ za pomocą klas MFC i podklas systemu Windows jest podobne funkcjonalnie, z wyjątkiem języka C++ nie obsługuje dynamicznego podklasy.

`CWnd`Klasa zapewnia połączenie między obiektem C++ (pochodnym od `CWnd` ) i obiektem okna systemu Windows (znanym jako `HWND` ).

Istnieją trzy typowe metody, które są związane z nimi:

- `CWnd` tworzy `HWND` . Możesz zmodyfikować zachowanie w klasie pochodnej, tworząc klasę pochodną `CWnd` . `HWND`Jest tworzony, gdy aplikacja wywołuje [CWnd:: Create](../mfc/reference/cwnd-class.md#create).

- Aplikacja dołącza `CWnd` do istniejącej `HWND` . Zachowanie istniejącego okna nie jest modyfikowane. Jest to przypadek delegowania i jest możliwy przez wywołanie [CWnd:: dołączanie](../mfc/reference/cwnd-class.md#attach) do aliasu istniejącego `HWND` do `CWnd` obiektu.

- `CWnd` jest dołączony do istniejącej `HWND` i można modyfikować zachowanie w klasie pochodnej. Jest to nazywane dynamicznym podklasą, ponieważ Zmieniamy zachowanie, a tym samym klasę obiektu systemu Windows w czasie wykonywania.

Można osiągnąć dynamiczną podklasę przy użyciu metod [CWnd:: SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) i[CWnd:: SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).

Obie procedury dołączają `CWnd` obiekt do istniejącego `HWND` . `SubclassWindow` Pobiera `HWND` bezpośrednio. `SubclassDlgItem` jest funkcją pomocnika, która przyjmuje identyfikator kontrolki i okno nadrzędne. `SubclassDlgItem` służy do dołączania obiektów C++ do kontrolek okna dialogowego utworzonych na podstawie szablonu okna dialogowego.

Zobacz przykład [CTRLTEST](../overview/visual-cpp-samples.md) , aby poznać kilka przykładów użycia `SubclassWindow` i `SubclassDlgItem` .

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
