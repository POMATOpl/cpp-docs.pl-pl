---
description: 'Dowiedz się więcej na temat: porady dotyczące narzędzi Toolbar'
title: Etykietki narzędzi paska narzędzi
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: bbf60246e778b60c2a6eacbcb55441806c00fad2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264287"
---
# <a name="toolbar-tool-tips"></a>Etykietki narzędzi paska narzędzi

Porady dotyczące narzędzi to małe okna podręczne, które stanowią krótkie opisy celu przycisku paska narzędzi, gdy przesuwasz wskaźnik myszy na przycisk przez pewien czas. Podczas tworzenia aplikacji za pomocą Kreatora aplikacji, który ma pasek narzędzi, zostanie dostarczona pomoc techniczna dla etykietki narzędzia. W tym artykule opisano obsługę etykietek narzędzi utworzonych przez Kreatora aplikacji oraz sposób dodawania do aplikacji obsługi etykietek narzędzi.

W tym artykule omówiono następujące zagadnienia:

- [Wskazówki dotyczące aktywowania narzędzia](#_core_activating_tool_tips)

- [Aktualizacje paska stanu Flyby](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a> Wskazówki dotyczące aktywowania narzędzia

Aby uaktywnić wskazówki dotyczące narzędzi w aplikacji, należy wykonać dwie czynności:

- Dodaj styl CBRS_TOOLTIPS do innych stylów (takich jak WS_CHILD, WS_VISIBLE i inne style **CBRS_** ) przekazaną jako parametr *DwStyle* do funkcji [CToolBar:: Create](../mfc/reference/ctoolbar-class.md#create) lub w [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle).

- Zgodnie z opisem w poniższej procedurze, Dołącz tekst etykietki paska narzędzi, oddzielone znakiem nowego wiersza ("\n") do zasobu ciągu zawierającego wiersz polecenia dla polecenia paska narzędzi. Zasób ciągu udostępnia identyfikator przycisku paska narzędzi.

#### <a name="to-add-the-tool-tip-text"></a>Aby dodać tekst etykietki narzędzia

1. Podczas edytowania paska narzędzi w edytorze paska narzędzi, Otwórz okno **Właściwości przycisku paska narzędzi** dla danego przycisku.

1. W oknie **monitu** określ tekst, który ma być wyświetlany w etykietce narzędzia dla tego przycisku.

> [!NOTE]
> Ustawienie tekstu jako właściwości przycisku w edytorze paska narzędzi zastępuje poprzednią procedurę, w której należało otworzyć i edytować zasób ciągu.

Jeśli pasek sterowania z włączonymi etykietami narzędzi ma kontrolki podrzędne umieszczone na niej, na pasku sterowania zostanie wyświetlona etykietka narzędzia dla każdej kontrolki podrzędnej na pasku sterowania, o ile spełnia ona następujące kryteria:

- Identyfikator kontrolki nie jest-1.

- Wpis tabeli ciągów o takim samym IDENTYFIKATORze jak formant podrzędny w pliku zasobu ma ciąg etykietki narzędzia.

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a> Aktualizacje paska stanu Flyby

Funkcja odnosząca się do etykietek narzędzi jest aktualizacją paska stanu "Flyby". Domyślnie komunikat na pasku stanu opisuje tylko określony przycisk paska narzędzi, gdy przycisk jest aktywowany. Dzięki dołączeniu CBRS_FLYBY na liście stylów przekazana do `CToolBar::Create` , można je zaktualizować, gdy kursor myszy przesuwa się nad paskiem narzędzi bez faktycznego uaktywniania przycisku.

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Implementacja paska narzędzi MFC (informacje ogólne na temat pasków narzędzi)](../mfc/mfc-toolbar-implementation.md)

- [Zadokowane i przestawne paski narzędzi](../mfc/docking-and-floating-toolbars.md)

- Klasy [CToolBar](../mfc/reference/ctoolbar-class.md) i [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [Praca z kontrolką paska narzędzi](../mfc/working-with-the-toolbar-control.md)

- [Używanie swoich starych pasków narzędzi](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Zobacz też

[Implementacja paska narzędzi MFC](../mfc/mfc-toolbar-implementation.md)
