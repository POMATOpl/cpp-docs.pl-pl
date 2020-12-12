---
description: 'Dowiedz się więcej na temat: przerywniki (C++)'
title: Przerywniki (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
ms.openlocfilehash: 7485ea82725c2221d32d0647123cfce473719ca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319433"
---
# <a name="punctuators-c"></a>Przerywniki (C++)

Przerywniki w języku C++ mają składnię i znaczenie semantyczne dla kompilatora, ale nie same, należy określić operację, która zwraca wartość. Niektóre przerywniki, pojedynczo lub w połączeniu, mogą również być operatorami języka C++ lub być znaczące dla preprocesora.

Dowolny z następujących znaków jest uznawany za przerywniki:

```
! % ^ & * ( ) - + = { } | ~
[ ] \ ; ' : " < > ? , . / #
```

Przerywniki **[]**, **()** i **{}** muszą występować w parach po [fazie translacji](../preprocessor/phases-of-translation.md) 4.

## <a name="see-also"></a>Zobacz też

[Konwencje leksykalne](../cpp/lexical-conventions.md)
