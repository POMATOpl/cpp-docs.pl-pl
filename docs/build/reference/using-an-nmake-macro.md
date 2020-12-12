---
description: 'Dowiedz się więcej na temat: korzystanie z makra NMAKE'
title: Korzystanie z makro NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: 14a1856b411bf7608b94caacb1b0b078dd1f5577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247010"
---
# <a name="using-an-nmake-macro"></a>Korzystanie z makro NMAKE

Aby użyć makra, należy ująć jego nazwę w nawiasy poprzedzone znakiem dolara ($) w następujący sposób.

## <a name="syntax"></a>Składnia

```
$(macroname)
```

## <a name="remarks"></a>Uwagi

Spacje nie są dozwolone. Nawiasy są opcjonalne, jeśli *makroname* jest pojedynczym znakiem. Ciąg definicji zastępuje $ (*Macroname*); niezdefiniowane makro jest zastępowane ciągiem o wartości null.

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

[Podstawianie makr](macro-substitution.md)

## <a name="see-also"></a>Zobacz też

[Makra i NMAKE](macros-and-nmake.md)
