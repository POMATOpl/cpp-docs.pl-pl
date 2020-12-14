---
description: 'Dowiedz się więcej na temat: Klasa CCmdUI'
title: Klasa CCmdUI
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 5fae6d2dda948fd3720a29d502d7f050e388bceb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216135"
---
# <a name="the-ccmdui-class"></a>Klasa CCmdUI

Gdy kieruje polecenie Update do programu obsługi, struktura przekazuje programowi obsługi wskaźnik do `CCmdUI` obiektu (lub do obiektu `CCmdUI` klasy pochodnej). Ten obiekt reprezentuje element menu lub przycisk paska narzędzi lub inny obiekt interfejsu użytkownika, który wygenerował polecenie. Procedura obsługi aktualizacji wywołuje funkcje składowe `CCmdUI` struktury za pomocą wskaźnika, aby zaktualizować obiekt interfejsu użytkownika. Na przykład poniżej przedstawiono procedurę obsługi aktualizacji dla elementu menu Wyczyść wszystko:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Ta procedura obsługi wywołuje `Enable` funkcję elementu członkowskiego obiektu z dostępem do elementu menu. `Enable` sprawia, że element jest dostępny do użycia.

## <a name="see-also"></a>Zobacz też

[Instrukcje: Aktualizowanie obiektów User-Interface](../mfc/how-to-update-user-interface-objects.md)
