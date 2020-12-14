---
description: 'Dowiedz się więcej na temat: Mapowanie komunikatów systemu Windows do klasy'
title: Mapowanie komunikatów systemu Windows na klasę
ms.date: 09/06/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
- Class Wizard [MFC]
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: cca13c4b262c6373fa3d968438331d5e0ce5f7d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280784"
---
# <a name="mapping-windows-messages-to-your-class"></a>Mapowanie komunikatów systemu Windows na klasę

Jeśli potrzebujesz okna dialogowego do obsługi komunikatów systemu Windows, Zastąp odpowiednie funkcje obsługi. Aby to zrobić, wybierz kartę **Widok klasy** w **Eksplorator rozwiązań**, kliknij prawym przyciskiem myszy klasę, która reprezentuje okno dialogowe, a następnie wybierz polecenie [Kreator klas](reference/mfc-class-wizard.md). Użyj kreatora, aby [zamapować komunikaty](reference/mapping-messages-to-functions.md) do klasy okna dialogowego. Spowoduje to zapisanie wpisu mapy komunikatów dla każdego komunikatu i dodanie funkcji składowych obsługi komunikatów do klasy. Użyj edytora kodu, aby napisać kod w programach obsługi komunikatów.

Można również przesłonić funkcje składowe [CDialog](reference/cdialog-class.md) i jej klas podstawowych, szczególnie [CWnd](reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Obsługa i mapowanie komunikatów](message-handling-and-mapping.md)

- [Powszechnie zastępowane funkcje składowe](commonly-overridden-member-functions.md)

- [Powszechnie dodawane funkcje składowe](commonly-added-member-functions.md)

## <a name="see-also"></a>Zobacz też

[Okna dialogowe](dialog-boxes.md)<br/>
[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)
