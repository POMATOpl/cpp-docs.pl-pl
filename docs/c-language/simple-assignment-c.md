---
description: 'Dowiedz się więcej na temat: przypisanie proste (C)'
title: Przypisanie proste (C)
ms.date: 11/04/2016
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
ms.openlocfilehash: bf8637268c810ed6a75095774ca6ff7b7d3d9e67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229902"
---
# <a name="simple-assignment-c"></a>Przypisanie proste (C)

Operator przypisywania prostego przypisuje jego prawy operand do lewego operandu. Wartość operandu Right jest konwertowana na typ wyrażenia przypisania i zastępuje wartość przechowywaną w obiekcie wydzielonym przez lewy argument operacji. Reguły konwersji dotyczące przypisywania są stosowane (zobacz [konwersje przypisań](../c-language/assignment-conversions.md)).

```
double x;
int y;

x = y;
```

W tym przykładzie wartość `y` jest konwertowana na typ **`double`** i przypisany do `x` .

## <a name="see-also"></a>Zobacz też

[Operatory przypisania języka C](../c-language/c-assignment-operators.md)
