---
description: 'Dowiedz się więcej o: Magazyn związków'
title: Magazyn złożeń
ms.date: 11/04/2016
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
ms.openlocfilehash: bd95f1c1955049299192d0b4dbd333c86aecce25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205281"
---
# <a name="storage-of-unions"></a>Magazyn złożeń

Magazyn skojarzony ze zmienną Union to magazyn wymagany dla największego elementu członkowskiego Unii. Gdy mniejsza składowa jest przechowywana, zmienna Union może zawierać nieużywane miejsce w pamięci. Wszystkie elementy członkowskie są przechowywane w tym samym obszarze pamięci i zaczynają się na tym samym adresie. Wartość przechowywana jest zastępowana za każdym razem, gdy wartość zostanie przypisana do innego elementu członkowskiego. Na przykład:

```
union         /* Defines a union named x */
{
    char *a, b;
    float f[20];
} x;
```

Elementy członkowskie `x` Unii są w kolejności ich deklaracji, wskaźnikiem do **`char`** wartości, **`char`** wartości i tablicą **`float`** wartości. Magazyn przydzielony do `x` jest magazynem wymaganym dla 20-elementowej tablicy `f` , ponieważ `f` jest najdłuższym członkiem Unii. Ponieważ żaden tag nie jest skojarzony z Unią, jego typ ma wartość unnamed lub "Anonymous".

## <a name="see-also"></a>Zobacz też

[Deklaracje Unii](../c-language/union-declarations.md)
