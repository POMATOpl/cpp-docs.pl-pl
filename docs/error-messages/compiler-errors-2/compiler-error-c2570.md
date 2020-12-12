---
description: 'Dowiedz się więcej o: błąd kompilatora C2570'
title: Błąd kompilatora C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: faebc117991262c8fff94ef75f18d6e59c884315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209025"
---
# <a name="compiler-error-c2570"></a>Błąd kompilatora C2570

"Identyfikator": Unia nie może mieć klas bazowych

Unia pochodzi od klasy, struktury lub związku. Jest to niedozwolone. Zadeklaruj typ pochodny jako klasę lub strukturę zamiast tego.

Poniższy przykład generuje C2570:

```cpp
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
