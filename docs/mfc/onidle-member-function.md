---
description: 'Dowiedz się więcej o: funkcja członkowska OnIdle'
title: OnIdle — Funkcja członkowska
ms.date: 11/19/2018
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: a094b72f78db75d9f0f93ffa840d1d90cc96294c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112261"
---
# <a name="onidle-member-function"></a>OnIdle — Funkcja członkowska

Gdy nie są przetwarzane żadne komunikaty systemu Windows, struktura [wywołuje funkcję elementu](reference/cwinapp-class.md#onidle) Członkowskiego [CWinApp](reference/cwinapp-class.md) (opisany w dokumentacji biblioteki MFC).

Przesłoń `OnIdle` , aby wykonać zadania w tle. Wersja domyślna aktualizuje stan obiektów interfejsu użytkownika, takich jak przyciski paska narzędzi i wykonuje czyszczenie tymczasowych obiektów utworzonych przez platformę w trakcie jego operacji. Na poniższej ilustracji pokazano, jak pętla jest wywoływana w `OnIdle` przypadku braku komunikatów w kolejce.

![Proces pętli komunikatów](../mfc/media/vc387c1.gif "Proces pętli komunikatów") <br/>
Pętla komunikatów

Aby uzyskać więcej informacji o tym, co można zrobić w pętli bezczynności, zobacz [przetwarzanie pętli bezczynności](idle-loop-processing.md).

## <a name="see-also"></a>Zobacz też

[CWinApp: Klasa aplikacji](cwinapp-the-application-class.md)
