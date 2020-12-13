---
description: 'Dowiedz się więcej o: błąd kompilatora C3297'
title: Błąd kompilatora C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 39cbdfe6bbc19341c904d6bae90a71595f388400
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144602"
---
# <a name="compiler-error-c3297"></a>Błąd kompilatora C3297

"constraint_2": nie można użyć "constraint_1" jako ograniczenia, ponieważ element "constraint_1" ma ograniczenie wartości

Klasy wartości są zapieczętowane. Jeśli ograniczenie jest klasą wartości, inne ograniczenie nigdy nie może pochodzić od niego.

Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3297.

```cpp
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```
