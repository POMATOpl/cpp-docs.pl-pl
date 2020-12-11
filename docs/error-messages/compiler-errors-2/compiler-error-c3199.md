---
description: 'Dowiedz się więcej o: błąd kompilatora C3199'
title: Błąd kompilatora C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 598d21edbddc91d39edb9623dc59537d3e27bdf3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155478"
---
# <a name="compiler-error-c3199"></a>Błąd kompilatora C3199

nieprawidłowe użycie zmiennoprzecinkowych pragm: wyjątki nie są obsługiwane w trybie bez dokładności

[Float_control](../../preprocessor/float-control.md) pragma została użyta do określenia modelu wyjątku zmiennoprzecinkowego w ustawieniu [/FP](../../build/reference/fp-specify-floating-point-behavior.md) innym niż **/FP: precyzyjne**.

Poniższy przykład generuje C3199:

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
