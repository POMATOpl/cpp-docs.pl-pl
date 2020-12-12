---
description: 'Dowiedz się więcej o: błąd kompilatora C3400'
title: Błąd kompilatora C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: d2ed88232f88c49f72c868e7b378aa0d6ef30ac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321958"
---
# <a name="compiler-error-c3400"></a>Błąd kompilatora C3400

cykliczna zależność ograniczenia obejmująca elementy "constraint_1" i "constraint_2"

Kompilator wykrył ograniczenia cykliczne.

Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3400.

```cpp
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```
