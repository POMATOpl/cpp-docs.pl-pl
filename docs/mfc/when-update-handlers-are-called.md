---
description: 'Dowiedz się więcej na temat: Kiedy są wywoływane programy obsługi aktualizacji'
title: Kiedy są wywoływane programy obsługi aktualizacji
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: ee5d402eea4121c9ceb4bcbd48e752549c55b1c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297177"
---
# <a name="when-update-handlers-are-called"></a>Kiedy są wywoływane programy obsługi aktualizacji

Załóżmy, że użytkownik kliknie mysz w menu plik, co spowoduje wygenerowanie komunikatu WM_INITMENUPOPUP. Mechanizm aktualizacji struktury zbiorczo aktualizuje wszystkie elementy w menu plik przed porzucaniem menu, aby użytkownik mógł je zobaczyć.

W tym celu struktura kieruje polecenia aktualizacji dla wszystkich elementów menu w menu podręcznym do standardowego routingu poleceń. Elementy docelowe poleceń w ramach routingu mają szansę zaktualizowania wszystkich elementów menu, dopasowując polecenie Update do odpowiedniego wpisu mapy komunikatów (formularza `ON_UPDATE_COMMAND_UI` ) i wywołując funkcję "procedura obsługi aktualizacji". W tym celu w przypadku menu z sześcioma elementami menu są wysyłane sześć poleceń aktualizacji. Jeśli istnieje procedura obsługi aktualizacji dla identyfikatora polecenia elementu menu, jest wywoływana, aby wykonać aktualizację. Jeśli nie, struktura sprawdza obecność programu obsługi dla tego identyfikatora polecenia i włącza lub wyłącza element menu stosownie do potrzeb.

Jeśli struktura nie znajdzie `ON_UPDATE_COMMAND_UI` wpisu podczas routingu poleceń, automatycznie włącza obiekt interfejsu użytkownika, jeśli istnieje `ON_COMMAND` wpis z tym samym identyfikatorem polecenia. W przeciwnym razie powoduje wyłączenie obiektu interfejsu użytkownika. W związku z tym, aby upewnić się, że obiekt interfejsu użytkownika jest włączony, podaj procedurę obsługi dla polecenia, które generuje lub dostarczą procedurę obsługi aktualizacji dla tego obiektu. Zobacz rysunek w temacie [obiekty interfejsu użytkownika i identyfikatory poleceń](../mfc/user-interface-objects-and-command-ids.md).

Istnieje możliwość wyłączenia domyślnego wyłączenia obiektów interfejsu użytkownika. Aby uzyskać więcej informacji, zobacz [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) składową klasy `CFrameWnd` w *Kompendium MFC*.

Inicjalizacja menu jest wykonywana automatycznie w strukturze, gdy aplikacja otrzymuje komunikat WM_INITMENUPOPUP. W pętli bezczynności struktura przeszukuje routing poleceń dla programów obsługi aktualizacji przycisków w taki sam sposób, jak w przypadku menu.

## <a name="see-also"></a>Zobacz też

[Instrukcje: Aktualizowanie obiektów User-Interface](../mfc/how-to-update-user-interface-objects.md)
