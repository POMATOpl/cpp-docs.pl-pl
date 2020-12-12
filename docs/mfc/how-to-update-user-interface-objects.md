---
description: 'Dowiedz się więcej na temat: jak aktualizować User-Interface obiektów'
title: 'Porady: aktualizowanie obiektów interfejsu użytkownika'
ms.date: 11/04/2016
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
ms.openlocfilehash: 32d7c033d03ba679fa295237c1c49c5060c731ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330171"
---
# <a name="how-to-update-user-interface-objects"></a>Porady: aktualizowanie obiektów interfejsu użytkownika

Zazwyczaj elementy menu i przyciski paska narzędzi mają więcej niż jeden stan. Na przykład element menu jest wyszarzony (wygaszony), jeśli jest niedostępny w obecnym kontekście. Elementy menu można także sprawdzić lub zaznaczyć. Przycisk paska narzędzi można także wyłączyć, jeśli jest niedostępny lub można go sprawdzić.

Kto aktualizuje stan tych elementów w wyniku zmiany warunków programu na logiczne, jeśli element menu generuje polecenie, które jest obsługiwane przez, mówi, że dokument ma aktualizację elementu menu. Dokument prawdopodobnie zawiera informacje, na których oparto aktualizację.

Jeśli polecenie ma wiele obiektów interfejsu użytkownika (prawdopodobnie element menu i przycisk paska narzędzi), obie są kierowane do tej samej funkcji obsługi. To hermetyzuje kod aktualizacji interfejsu użytkownika dla wszystkich odpowiedników obiektów interfejsu użytkownika w jednym miejscu.

Struktura zapewnia wygodny interfejs do automatycznego aktualizowania obiektów interfejsu użytkownika. Możesz zdecydować się na aktualizację w inny sposób, ale udostępniony interfejs jest wydajny i łatwy w użyciu.

W poniższych tematach opisano sposób używania programów obsługi aktualizacji:

- [Kiedy są wywoływane programy obsługi aktualizacji](when-update-handlers-are-called.md)

- [ON_UPDATE_COMMAND_UI makro](on-update-command-ui-macro.md)

- [CCmdUI, klasa](the-ccmdui-class.md)

## <a name="see-also"></a>Zobacz też

[Menu](menus-mfc.md)
