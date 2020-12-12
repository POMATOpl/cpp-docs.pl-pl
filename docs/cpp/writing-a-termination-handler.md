---
description: 'Dowiedz się więcej o: pisaniu programu obsługi zakończenia'
title: Pisanie programu obsługi zakończenia
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
ms.openlocfilehash: a203cab7d61be66c5fe919aefe1895aa0928c5d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302988"
---
# <a name="writing-a-termination-handler"></a>Pisanie programu obsługi zakończenia

W przeciwieństwie do programu obsługi wyjątków, program obsługi zakończenia jest zawsze wykonywany, niezależnie od tego, czy chroniony blok kodu został zakończony normalnie. Jedynym celem programu obsługi zakończenia powinna być upewnienie się, że zasoby, takie jak pamięć, uchwyty i pliki, są prawidłowo zamknięte niezależnie od tego, jak sekcja kodu kończy wykonywanie.

Programy obsługi zakończenia używają instrukcji try-finally.

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Instrukcja try-finally](../cpp/try-finally-statement.md)

- [Oczyszczanie zasobów](../cpp/cleaning-up-resources.md)

- [Chronometraż akcji w obsłudze wyjątków](../cpp/timing-of-exception-handling-a-summary.md)

- [Ograniczenia dotyczące programu obsługi zakończenia](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>Zobacz też

[Obsługa wyjątków strukturalnych (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
