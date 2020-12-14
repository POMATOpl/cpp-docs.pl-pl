---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4694'
title: Ostrzeżenie kompilatora C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: f6a6890fab320c2471381076707eeca30ce3e99b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315078"
---
# <a name="compiler-warning-c4694"></a>Ostrzeżenie kompilatora C4694

> "*Class*": zapieczętowana Klasa abstrakcyjna nie może mieć klasy bazowej "*BASE_CLASS*"

Klasa abstrakcyjna i zapieczętowana nie może dziedziczyć z typu referencyjnego; Klasa zapieczętowana i abstrakcyjna nie może implementować funkcji klasy bazowej ani nie zezwalać na używanie jej jako klasy bazowej.

Aby uzyskać więcej informacji, zobacz [abstrakcyjne](../../extensions/abstract-cpp-component-extensions.md), [zapieczętowane](../../extensions/sealed-cpp-component-extensions.md)i [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md).

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4694.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```
