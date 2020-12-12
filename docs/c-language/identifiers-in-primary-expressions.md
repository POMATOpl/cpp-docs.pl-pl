---
description: 'Dowiedz się więcej o: identyfikatory w wyrażeniach podstawowych'
title: Identyfikatory w wyrażeniach podstawowych
ms.date: 11/04/2016
helpviewer_keywords:
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
ms.openlocfilehash: 63fbadeb786edda232282a5073dd85b22f487e9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182180"
---
# <a name="identifiers-in-primary-expressions"></a>Identyfikatory w wyrażeniach podstawowych

Identyfikatory mogą mieć typ całkowity, **`float`** , **`enum`** ,, **`struct`** **`union`** , tablicę, wskaźnik lub funkcję. Identyfikator jest wyrażeniem podstawowym, pod warunkiem że został zadeklarowany jako wyznaczanie obiektu (w tym przypadku jest to wartość l) lub jako funkcja (w tym przypadku jest to oznaczenie funkcji). Patrz [wyrażenia wartości l i R](../c-language/l-value-and-r-value-expressions.md) dla definicji l-wartości.

Wartość wskaźnika reprezentowana przez identyfikator tablicy nie jest zmienną, więc identyfikator tablicy nie może tworzyć operandu po lewej stronie przypisania i w związku z tym nie jest to modyfikowalna wartość l.

Identyfikator zadeklarowany jako funkcja reprezentuje wskaźnik, którego wartość jest adresem funkcji. Wskaźnik odnosi się do funkcji zwracającej wartość określonego typu. W ten sposób identyfikatory funkcji nie mogą również zawierać wartości l w operacjach przypisywania. Aby uzyskać więcej informacji, zobacz temat [Identyfikatory](../c-language/c-identifiers.md).

## <a name="see-also"></a>Zobacz też

[Wyrażenia podstawowe języka C](../c-language/c-primary-expressions.md)
