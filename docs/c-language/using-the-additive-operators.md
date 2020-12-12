---
description: 'Dowiedz się więcej na temat: korzystanie z operatorów dodatków'
title: Używanie dodatkowych operatorów
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
ms.openlocfilehash: d56a1b2e2696ae88598306271ed02c417ef63b0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318367"
---
# <a name="using-the-additive-operators"></a>Używanie dodatkowych operatorów

Poniższe przykłady, które ilustrują operatory dodawania i odejmowania, wykorzystują następujące deklaracje:

```
int i = 4, j;
float x[10];
float *px;
```

Te instrukcje są równoważne:

```
px = &x[4 + i];
px = &x[4] + i;
```

Wartość `i` jest mnożona przez długość **`float`** i dodana do `&x[4]` . Wartość wskaźnika będącego wynikiem jest adres `x[8]` .

```
j = &x[i] - &x[i-2];
```

W tym przykładzie adres trzeciego elementu `x` (określony przez `x[i-2]` ) jest odejmowany od adresu piątego elementu `x` (podaną przez `x[i]` ). Różnica jest dzielona przez długość a **`float`** ; wynik jest wartością całkowitą 2.

## <a name="see-also"></a>Zobacz też

[Operatory addytywne języka C](../c-language/c-additive-operators.md)
