---
description: 'Dowiedz się więcej na temat: wyświetlanie potwierdzeń'
title: Wyświetlanie potwierdzeń
ms.date: 05/05/2019
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
ms.openlocfilehash: 3f925d5f3a7d1ad0ac1171ea8983b57ead147bf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153017"
---
# <a name="displaying-assertions"></a>Wyświetlanie potwierdzeń

Jeśli klient połączony z usługą wydaje się przestać odpowiadać, usługa mogła zostać potwierdzona i wyświetlone okno komunikatu, którego nie można zobaczyć. Można to potwierdzić przy użyciu debugera programu Visual Studio do debugowania kodu (zobacz sekcję [using Task Manager](../atl/using-task-manager.md) wcześniej w tej sekcji).

Jeśli okaże się, że usługa wyświetla okno komunikatu, którego nie można zobaczyć, przed ponownym użyciem usługi należy ustawić opcję **Zezwalaj usłudze na współdziałanie z pulpitem** . Ta opcja jest parametrem uruchamiania, który umożliwia wyświetlenie wszystkich okien komunikatów wyświetlanych przez usługę na pulpicie. Aby ustawić tę opcję, Otwórz Panel sterowania usług, wybierz usługę, kliknij przycisk **Start**, a następnie wybierz opcję **Zezwalaj usłudze na współpracujące z pulpitem** .

## <a name="see-also"></a>Zobacz też

[Porady dotyczące debugowania](../atl/debugging-tips.md)
