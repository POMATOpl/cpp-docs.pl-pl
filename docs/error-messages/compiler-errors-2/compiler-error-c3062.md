---
title: C3062 błąd kompilatora
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: ac45847c94e7d2dc731eba71b0a38105eb915e53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590414"
---
# <a name="compiler-error-c3062"></a>C3062 błąd kompilatora

"enum": moduł wyliczający wymaga wartości, ponieważ podstawowy typ to "type"

Można określić typu podstawowego dla wyliczenia. Jednak niektóre typy wymagają przypisania wartości do każdego modułu wyliczającego.

Aby uzyskać więcej informacji na temat typów wyliczeniowych, zobacz [klasa wyliczeniowa](../../windows/enum-class-cpp-component-extensions.md).

Poniższy przykład spowoduje wygenerowanie C3062:

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```