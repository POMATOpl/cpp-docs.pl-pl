---
description: 'Dowiedz się więcej o: błąd kompilatora C3388'
title: Błąd kompilatora C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: 0acc4729b5b6de61476bc134b9ef7f79bb9e86e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285529"
---
# <a name="compiler-error-c3388"></a>Błąd kompilatora C3388

"Type": niedozwolone jako ograniczenie, przy założeniu, że element "ref class" będzie kontynuował analizowanie

Określono ograniczenie dla typu ogólnego, ale ograniczenie nie zostało prawidłowo określone. Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3388.

```cpp
// C3388.cpp
// compile with: /clr /c
interface class AA {};

generic <class T>
where T : interface class   // C3388
ref class C {};

// OK
generic <class T>
where T : AA
ref class D {};
```
