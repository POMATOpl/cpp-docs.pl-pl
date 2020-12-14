---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4570'
title: Ostrzeżenie kompilatora (poziom 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: aa776654b77f8d548f197ac2dc35bd4474e92068
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257774"
---
# <a name="compiler-warning-level-3-c4570"></a>Ostrzeżenie kompilatora (poziom 3) C4570

"Type": nie jest jawnie zadeklarowany jako abstrakcyjny, ale ma funkcje abstrakcyjne

Typ, który zawiera funkcje [abstrakcyjne](../../extensions/abstract-cpp-component-extensions.md) , powinien być oznaczony jako abstrakcyjny.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4570.

```cpp
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```
