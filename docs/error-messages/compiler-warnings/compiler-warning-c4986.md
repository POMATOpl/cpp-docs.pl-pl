---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4986'
title: Ostrzeżenie kompilatora C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: 5d068ee376c6ae6ce1fb3563d66c7bda871da0ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336048"
---
# <a name="compiler-warning-c4986"></a>Ostrzeżenie kompilatora C4986

"Function": Specyfikacja wyjątku nie jest zgodna z poprzednią deklaracją

To ostrzeżenie można wygenerować, gdy istnieje Specyfikacja wyjątku w jednej deklaracji, a nie druga.

Domyślnie C4986 jest wyłączona. Aby uzyskać więcej informacji, zobacz [ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C4986.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1()
{
    // ...
}
```

Poniższy przykład eliminuje to ostrzeżenie.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```
