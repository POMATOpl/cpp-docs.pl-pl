---
description: 'Dowiedz się więcej o: definiowaniu makra NMAKE'
title: Definiowanie makro NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: 133e05cac2a236a38f6b2d1e719f1b66fd73760d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201641"
---
# <a name="defining-an-nmake-macro"></a>Definiowanie makro NMAKE

## <a name="syntax"></a>Składnia

```

macroname=string
```

## <a name="remarks"></a>Uwagi

*Makroname* jest kombinacją liter, cyfr i podkreśleń (_) do 1 024 znaków i uwzględnia wielkość liter. *Makroname* może zawierać wywołane makro. Jeśli *makro* zawiera wyłącznie wywołane makro, wywoływane makro nie może mieć wartości null ani być niezdefiniowane.

`string`Może to być dowolna sekwencja zero lub więcej znaków. Ciąg pusty zawiera zero znaków lub tylko spacje lub znaki tabulacji. `string`Może zawierać wywołanie makra.

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

[Znaki specjalne w makrach](special-characters-in-macros.md)

[Makra niezdefiniowane oraz makra o wartości zerowej](null-and-undefined-macros.md)

[Miejsce definiowania makr](where-to-define-macros.md)

[Pierwszeństwo w definicjach makr](precedence-in-macro-definitions.md)

## <a name="see-also"></a>Zobacz też

[Makra i NMAKE](macros-and-nmake.md)
