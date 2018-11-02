---
title: Błąd krytyczny C1104
ms.date: 11/04/2016
f1_keywords:
- C1104
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
ms.openlocfilehash: c10d1a89d854aaeac47a9a70f1e1e319d1662935
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520288"
---
# <a name="fatal-error-c1104"></a>Błąd krytyczny C1104

krytyczny błąd importu libid: "message"

Kompilator wykrył problem podczas importowania biblioteki typów.  Na przykład nie można określić bibliotekę typów z identyfikatora libid i również określić `no_registry`.

Aby uzyskać więcej informacji, zobacz [#import Directive](../../preprocessor/hash-import-directive-cpp.md).

Poniższy przykład spowoduje wygenerowanie C1104:

```
// C1104.cpp
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104
```