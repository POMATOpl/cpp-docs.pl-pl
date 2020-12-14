---
description: 'Dowiedz się więcej na temat: podstawy pasków narzędzi'
title: Paski narzędzi — podstawowe założenia
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
ms.openlocfilehash: ed52c5878482f2ff0fa1c31a133fd2948d21a76e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264391"
---
# <a name="toolbar-fundamentals"></a>Paski narzędzi — podstawowe założenia

W tym artykule opisano podstawową implementację MFC, która umożliwia dodanie domyślnego paska narzędzi do aplikacji przez wybranie opcji w Kreatorze aplikacji. Omawiane tematy to m.in.:

- [Opcja paska narzędzi Kreatora aplikacji](#_core_the_appwizard_toolbar_option)

- [Pasek narzędzi w kodzie](#_core_the_toolbar_in_code)

- [Edytowanie zasobu paska narzędzi](#_core_editing_the_toolbar_resource)

- [Wiele pasków narzędzi](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a> Opcja paska narzędzi Kreatora aplikacji

Aby uzyskać jeden pasek narzędzi z domyślnymi przyciskami, wybierz opcję Pasek narzędzi dokowania standardowa na stronie z etykietą funkcje interfejsu użytkownika. Spowoduje to dodanie kodu do aplikacji, która:

- Tworzy obiekt Toolbar.

- Zarządza paskiem narzędzi, w tym możliwością dokowania lub do wartości zmiennoprzecinkowej.

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a> Pasek narzędzi w kodzie

Pasek narzędzi jest obiektem [CToolBar](../mfc/reference/ctoolbar-class.md) zadeklarowanym jako element członkowski danych `CMainFrame` klasy aplikacji. Innymi słowy, obiekt Toolbar jest osadzony w głównym obiekcie okna ramki. Oznacza to, że MFC tworzy pasek narzędzi podczas tworzenia okna ramki i niszczy pasek narzędzi, gdy niszczy okno ramki. Poniższa deklaracja klasy częściowej dla aplikacji interfejsu wielu dokumentów (MDI) zawiera elementy członkowskie danych dla osadzonego paska narzędzi i osadzony pasek stanu. Pokazuje również przesłonięcie `OnCreate` funkcji składowej.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Tworzenie paska narzędzi odbywa się w programie `CMainFrame::OnCreate` . Wywołania MFC są [tworzone](../mfc/reference/cwnd-class.md#oncreate) po utworzeniu okna dla ramki, ale zanim staną się widoczne. Domyślnie `OnCreate` generowane przez Kreatora aplikacji wykonuje następujące zadania paska narzędzi:

1. Wywołuje `CToolBar` funkcję [tworzenia](../mfc/reference/ctoolbar-class.md#create) elementu członkowskiego obiektu w celu utworzenia bazowego obiektu [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) .

1. Wywołuje [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) w celu załadowania informacji o zasobach paska narzędzi.

1. Wywołuje funkcje do włączania zadokowanych, zmiennoprzecinkowych i etykietek narzędzi. Szczegółowe informacje o tych wywołaniach znajdują się w artykule [dokowanie i przestawne paski narzędzi](../mfc/docking-and-floating-toolbars.md).

> [!NOTE]
> Ogólna Przykładowa [DOCKTOOL](../overview/visual-cpp-samples.md) MFC zawiera ilustracje starych i nowych pasków narzędzi MFC. Paski narzędzi, które używają `COldToolbar` wymaganych wywołań w kroku 2 do `LoadBitmap` (a nie `LoadToolBar` ) i do `SetButtons` . Nowe paski narzędzi wymagają wywołań do `LoadToolBar` .

Wywołania dotyczące dokowania, zmiennoprzecinkowe i narzędzia są opcjonalne. Możesz usunąć te wiersze z `OnCreate` , jeśli wolisz. Wynik jest paskiem narzędzi, który pozostanie stały, nie można go przepływać ani zadokować i nie można wyświetlić etykietek narzędzi.

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a> Edytowanie zasobu paska narzędzi

Domyślny pasek narzędzi uzyskany za pomocą Kreatora aplikacji jest oparty na **RT_TOOLBAR** zasobem niestandardowym wprowadzonym w bibliotece MFC w wersji 4,0. Ten zasób można edytować za pomocą [edytora pasków narzędzi](../windows/toolbar-editor.md). Edytor pozwala łatwo dodawać, usuwać i zmieniać rozmieszczenie przycisków. Zawiera on graficzny Edytor przycisków, które są bardzo podobne do ogólnego edytora grafiki w Visual C++. Jeśli edytowano paski narzędzi w poprzednich wersjach Visual C++, zadanie jest znacznie łatwiejsze.

Aby połączyć przycisk paska narzędzi z poleceniem, nadajesz przyciskowi identyfikator polecenia, na przykład `ID_MYCOMMAND` . Określ identyfikator polecenia na stronie Właściwości przycisku w edytorze paska narzędzi. Następnie Utwórz funkcję obsługi dla polecenia (zobacz [Mapowanie komunikatów do funkcji](../mfc/reference/mapping-messages-to-functions.md) , aby uzyskać więcej informacji).

Nowe funkcje składowe [CToolBar](../mfc/reference/ctoolbar-class.md) współpracują z zasobem **RT_TOOLBAR** . [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) teraz miejsce [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) do załadowania mapy bitowej obrazów przycisków paska narzędzi i [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) w celu ustawienia stylów przycisków i połączenia przycisków z obrazami mapy bitowej.

Aby uzyskać szczegółowe informacje o używaniu edytora pasków narzędzi, zobacz [Edytor paska narzędzi](../windows/toolbar-editor.md).

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a> Wiele pasków narzędzi

Kreator aplikacji udostępnia jeden domyślny pasek narzędzi. Jeśli potrzebujesz więcej niż jednego paska narzędzi w aplikacji, możesz modelować kod dla dodatkowych pasków narzędzi w oparciu o kod wygenerowany przez kreatora dla domyślnego paska narzędzi.

Jeśli chcesz wyświetlić pasek narzędzi jako wynik polecenia, musisz wykonać następujące działania:

- Utwórz nowy zasób paska narzędzi za pomocą edytora pasków narzędzi i załaduj go przy `OnCreate` użyciu funkcji składowej [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) .

- Osadź nowy obiekt [CToolBar](../mfc/reference/ctoolbar-class.md) w głównej klasie okna ramki.

- Ustaw odpowiednie wywołania funkcji w programie w `OnCreate` celu zadokowania lub przesunięcia paska narzędzi, ustawienia jego stylu itd.

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Implementacja paska narzędzi MFC (informacje ogólne na temat pasków narzędzi)](../mfc/mfc-toolbar-implementation.md)

- [Zadokowane i przestawne paski narzędzi](../mfc/docking-and-floating-toolbars.md)

- [Etykietki narzędzi paska narzędzi](../mfc/toolbar-tool-tips.md)

- Klasy [CToolBar](../mfc/reference/ctoolbar-class.md) i [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [Praca z kontrolką paska narzędzi](../mfc/working-with-the-toolbar-control.md)

- [Używanie swoich starych pasków narzędzi](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Zobacz też

[Implementacja paska narzędzi MFC](../mfc/mfc-toolbar-implementation.md)
