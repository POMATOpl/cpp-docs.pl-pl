---
description: 'Dowiedz się więcej o: błąd kompilatora C3062'
title: Błąd kompilatora C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: b57d03f3ef09e1d01741866d99dfff87aa5aa28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281746"
---
# <a name="compiler-error-c3062"></a>Błąd kompilatora C3062

"enum": moduł wyliczający wymaga wartości, ponieważ typ podstawowy to "Type"

Można określić typ podstawowy dla wyliczenia. Jednak niektóre typy wymagają przypisania wartości do poszczególnych modułów wyliczających.

Aby uzyskać więcej informacji na temat typów wyliczeniowych, zobacz [enum Class](../../extensions/enum-class-cpp-component-extensions.md).

Poniższy przykład generuje C3062:

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
