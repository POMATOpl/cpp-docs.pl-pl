---
description: 'Dowiedz się więcej o: błąd kompilatora C3219'
title: Błąd kompilatora C3219
ms.date: 11/04/2016
f1_keywords:
- C3219
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
ms.openlocfilehash: 0210d8c65972a6adc7d5c2dbe51088f3c3766106
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267745"
---
# <a name="compiler-error-c3219"></a>Błąd kompilatora C3219

"param": parametr generyczny nie może być ograniczony przez wiele interfejsów, które nie są interfejsami: "Class"

Nie można ograniczyć parametru generycznego przez dwie lub więcej zarządzanych klas.

Poniższy przykład generuje C3219:

```cpp
// C3219.cpp
// compile with: /clr
ref class A {};
ref class B {};

generic <class T>
where T : A, B
ref class E {};   // C3219
```

Poniższy przykład demonstruje możliwe rozwiązanie:

```cpp
// C3219b.cpp
// compile with: /clr /c
ref class A {};

interface struct C {};

generic <class T>
where T : A
ref class E {};
```
