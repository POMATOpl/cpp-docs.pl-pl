---
description: 'Dowiedz się więcej o: błąd kompilatora C3271'
title: Błąd kompilatora C3271
ms.date: 11/04/2016
f1_keywords:
- C3271
helpviewer_keywords:
- C3271
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
ms.openlocfilehash: 62ff98d27757aa8f339d99aa6a10d50bf7503a27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113664"
---
# <a name="compiler-error-c3271"></a>Błąd kompilatora C3271

"member": nieprawidłowa wartość "value" atrybutu FieldOffset

Liczba ujemna została przeniesiona do atrybutu **FieldOffset** .

Poniższy przykład generuje C3271:

```cpp
// C3271.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
value class MyStruct1 {
   public: [FieldOffset(0)] int a;
   public: [FieldOffset(-1)] long b;   // C3271
};
```
