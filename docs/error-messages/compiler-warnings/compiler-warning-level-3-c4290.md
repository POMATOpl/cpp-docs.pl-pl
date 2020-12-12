---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4290'
title: Ostrzeżenie kompilatora (poziom 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 771eb01c23778a716aee22ca747ea6473909a8bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344071"
---
# <a name="compiler-warning-level-3-c4290"></a>Ostrzeżenie kompilatora (poziom 3) C4290

Zignorowano specyfikację wyjątku C++ z wyjątkiem wskazuje, że funkcja nie jest __declspec (nothrow)

Funkcja jest zadeklarowana przy użyciu specyfikacji wyjątku, która Visual C++ akceptuje, ale nie implementuje. Kod ze specyfikacjami wyjątków, które są ignorowane podczas kompilowania, może być konieczne ponowne skompilowanie i połączenie z użyciem ich ponownie w przyszłych wersjach obsługujących specyfikacje wyjątków.

Aby uzyskać więcej informacji, zobacz [specyfikacje wyjątków (throw)](../../cpp/exception-specifications-throw-cpp.md) .

Można uniknąć tego ostrzeżenia przy użyciu dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) :

```cpp
#pragma warning( disable : 4290 )
```

Następujący przykładowy kod generuje C4290:

```cpp
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```
