---
description: 'Dowiedz się więcej na temat: powiadomienia wysyłane przez formanty animacji'
title: Powiadomienia wysyłane przez formanty animacji
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 17dbd041e1c22b8d6542e64fd8b99d86389ea2d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280563"
---
# <a name="notifications-sent-by-animation-controls"></a>Powiadomienia wysyłane przez formanty animacji

Kontrolka animacji ([Korzystanie CAnimateCtrl](reference/canimatectrl-class.md)) wysyła dwa różne typy komunikatów powiadomień. Powiadomienia są wysyłane w formie [WM_COMMAND](/windows/win32/menurc/wm-command) komunikatów.

Komunikat [ACN_START](/windows/win32/Controls/acn-start) jest wysyłany po rozpoczęciu odtwarzania klipu przez kontrolkę animacji. Komunikat [ACN_STOP](/windows/win32/Controls/acn-stop) jest wysyłany po zakończeniu lub zatrzymaniu odtwarzania klipu przez kontrolkę animacji.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CAnimateCtrl](using-canimatectrl.md)<br/>
[Formanty](controls-mfc.md)
