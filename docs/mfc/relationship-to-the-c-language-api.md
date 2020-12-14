---
description: 'Dowiedz się więcej na temat: relacja z interfejsem API języka C'
title: Relacja z interfejsem API języka C
ms.date: 11/04/2016
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: fdfc03d9e8379ee4f19452ce81cba9957930bfe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218072"
---
# <a name="relationship-to-the-c-language-api"></a>Relacja z interfejsem API języka C

Pojedyncza cecha, która ustawia bibliotekę Microsoft Foundation Class (MFC), poza innymi bibliotekami klas dla systemu Windows, to bardzo bliskie mapowanie do interfejsu API systemu Windows zapisywanego w języku C. Dodatkowo można na ogół mieszać wywołania biblioteki klas swobodnie za pomocą bezpośrednich wywołań interfejsu API systemu Windows. Ten bezpośredni dostęp nie oznacza jednak, że klasy są kompletną wymianą dla tego interfejsu API. Deweloperzy nadal muszą czasami wykonać bezpośrednie wywołania niektórych funkcji systemu Windows, takich jak [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) i [GetSystemMetrics](/windows/win32/api/winuser/nf-winuser-getsystemmetrics), na przykład. Funkcja systemu Windows jest opakowana przez funkcję składową klasy tylko wtedy, gdy istnieje oczywista korzyść.

Ponieważ czasami trzeba wykonać natywne wywołania funkcji systemu Windows, należy mieć dostęp do dokumentacji interfejsu API systemu Windows w języku C. Ta dokumentacja jest dołączona do Microsoft Visual C++.

> [!NOTE]
> Aby zapoznać się z omówieniem działania struktury biblioteki MFC, zobacz [Używanie klas do pisania aplikacji dla systemu Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>Zobacz też

[Ogólne zasady projektowania klas](../mfc/general-class-design-philosophy.md)
