---
description: 'Dowiedz się więcej o: błąd kompilatora C3353'
title: Błąd kompilatora C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: 50ff7a6b104f3e16ce17f1398da49a146c0d41a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335047"
---
# <a name="compiler-error-c3353"></a>Błąd kompilatora C3353

"delegat": delegat może być utworzony tylko z globalnej funkcji lub funkcji składowej typu zarządzanego lub WinRT

Delegaty zadeklarowane za pomocą słowa kluczowego [delegata](../../extensions/delegate-cpp-component-extensions.md) mogą być deklarowane tylko w zakresie globalnym.

Poniższy przykład generuje C3353:

```cpp
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```
