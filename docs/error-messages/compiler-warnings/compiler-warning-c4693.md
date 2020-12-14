---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4693'
title: Ostrzeżenie kompilatora C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: 114809e1f73eb3d4e3481f0baa348d5eb478f4f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315104"
---
# <a name="compiler-warning-c4693"></a>Ostrzeżenie kompilatora C4693

> "Class": zapieczętowana Klasa abstrakcyjna nie może mieć żadnych składowych wystąpienia "test"

Jeśli typ jest oznaczony jako [Sealed](../../extensions/sealed-cpp-component-extensions.md) i [abstract](../../extensions/abstract-cpp-component-extensions.md), może mieć tylko statyczne elementy członkowskie.

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4693.

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```
