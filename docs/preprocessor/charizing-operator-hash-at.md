---
description: 'Dowiedz się więcej o: Operator konwersji na znaki (# @)'
title: Operator konwersji na znaki (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 6d04aa24c75153957bd6fd09824f4e94e36fd38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300869"
---
# <a name="charizing-operator-"></a>Operator konwersji na znaki (#@)

**Specyficzne dla firmy Microsoft**

Operatora konwersji na znaki można używać tylko z argumentami makr. Jeśli `#@` poprzedza parametr formalny w definicji makra, rzeczywisty argument jest ujęty w znaki pojedynczego cudzysłowu i traktowany jako znak, gdy makro jest rozwinięte. Na przykład:

```cpp
#define makechar(x)  #@x
```

powoduje, że instrukcja

```cpp
a = makechar(b);
```

Aby można było rozwijać

```cpp
a = 'b';
```

Znak pojedynczego cudzysłowu ( `'` ) nie może być używany z operatorem konwersji na znaki.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Operatory preprocesora](../preprocessor/preprocessor-operators.md)
