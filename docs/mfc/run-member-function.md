---
description: 'Dowiedz się więcej na temat: Uruchom funkcję członkowską'
title: Uruchamianie funkcji członkowskiej
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: ae67c6b02344a65735ce06775b1d1788d1dabf2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217825"
---
# <a name="run-member-function"></a>Uruchamianie funkcji członkowskiej

Aplikacja struktury spędza większość czasu w funkcji elementu członkowskiego [uruchamiania](../mfc/reference/cwinapp-class.md#run) klasy [CWinApp](../mfc/reference/cwinapp-class.md). Po zainicjowaniu program `WinMain` wywołuje `Run` pętlę komunikatów.

`Run` przechodzi przez pętlę komunikatów, sprawdzając kolejkę komunikatów dla dostępnych komunikatów. Jeśli komunikat jest dostępny, `Run` wysyła go do działania. Jeśli nie są dostępne żadne komunikaty, które często są prawdziwe, program `Run` wywołuje `OnIdle` wykonywanie wszelkich operacji przetwarzania w czasie bezczynności. Jeśli nie ma żadnych komunikatów i nie trwa przetwarzanie bezczynne, aplikacja czeka, aż wystąpi coś. Gdy aplikacja zakończy działanie, program `Run` wywołuje polecenie `ExitInstance` . Rysunek w [funkcji członkowskiej OnIdle](../mfc/onidle-member-function.md) pokazuje sekwencję akcji w pętli komunikatów.

Wysyłanie komunikatów zależy od rodzaju wiadomości. Aby uzyskać więcej informacji, zobacz [komunikaty i polecenia w strukturze](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Zobacz też

[CWinApp: Klasa aplikacji](../mfc/cwinapp-the-application-class.md)
