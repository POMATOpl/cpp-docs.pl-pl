---
description: 'Dowiedz się więcej na temat: Type-Safe dostępu do kontrolek bez użycia kreatorów kodu'
title: Bezpieczny dostęp do kontrolek bez użycia kreatorów kodu
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
ms.openlocfilehash: 1e59353a17f0d841cd69fa64f792dcc7cdbfa6ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263780"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Bezpieczny dostęp do kontrolek bez użycia kreatorów kodu

Pierwsze podejście do tworzenia bezpiecznego dostępu do formantów przy użyciu wbudowanej funkcji składowej do rzutowania zwracanego typu `CWnd` `GetDlgItem` funkcji składowej klasy na odpowiedni typ kontrolki C++, jak w poniższym przykładzie:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Następnie można użyć tej funkcji elementu członkowskiego, aby uzyskać dostęp do kontrolki w sposób bezpieczny dla typu przy użyciu kodu podobnego do poniższego:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>Zobacz też

[Bezpieczny dostęp do kontrolek w oknie dialogowym](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Bezpieczny dostęp do kontrolek z użyciem kreatorów kodu](../mfc/type-safe-access-to-controls-with-code-wizards.md)
