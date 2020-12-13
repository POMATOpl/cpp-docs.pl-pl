---
description: 'Dowiedz się więcej o: błąd kompilatora C3363'
title: Błąd kompilatora C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: b746a4c1e220ee05f96f3f2ceae524d5747550d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335032"
---
# <a name="compiler-error-c3363"></a>Błąd kompilatora C3363

"Type": "typeid" może być stosowany tylko do typu

Operator [typeid](../../extensions/typeid-cpp-component-extensions.md) został niepoprawnie użyty.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3363.

```cpp
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```
