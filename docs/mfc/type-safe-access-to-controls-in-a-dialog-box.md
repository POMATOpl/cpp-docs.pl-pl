---
description: 'Dowiedz się więcej na temat: Type-Safe dostępu do kontrolek w oknie dialogowym'
title: Bezpieczny dostęp do formantów w oknie dialogowym
ms.date: 11/04/2016
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
ms.openlocfilehash: 1c8b3482ee723e95142c9cd19fa6068f32f4ebd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263832"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Bezpieczny dostęp do formantów w oknie dialogowym

Kontrolki w oknie dialogowym mogą używać interfejsów klas formantów MFC, takich jak `CListBox` i `CEdit` . Użytkownik może sam utworzyć obiekt formantu i dołączyć go do formantu w oknie dialogowym. Tak powstały formant będzie dostępny za pośrednictwem jego interfejsu klasy. W interfejsie można wywoływać funkcje składowe w celu wykonania różnych operacji na formancie. Opisane tutaj metody umożliwiają bezpieczny dostęp do formantu. Jest to szczególnie użyteczne w przypadku formantów takich jak pola listy i pola edycji.

Istnieją dwa podejścia do nawiązywania połączenia między kontrolką w oknie dialogowym a zmienną elementu członkowskiego kontrolki języka C++ w `CDialog` klasie pochodnej:

- [Bez kreatorów kodu](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [Za pomocą kreatorów kodu](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>Zobacz też

[Okna dialogowe](../mfc/dialog-boxes.md)
