---
description: 'Dowiedz się więcej o: błąd kompilatora C2071'
title: Błąd kompilatora C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: ec5a08150b322ca5ce3a973a4e65d71ed410e25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323197"
---
# <a name="compiler-error-c2071"></a>Błąd kompilatora C2071

"Identyfikator": niedozwolona Klasa magazynu

`identifier` został zadeklarowany za pomocą nieprawidłowej [klasy magazynu](../../c-language/c-storage-classes.md). Ten błąd może być spowodowany tym, że dla identyfikatora określono więcej niż jedną klasę magazynu, lub gdy definicja jest niezgodna z deklaracją klasy magazynu.

Aby rozwiązać ten problem, zapoznaj się z zamierzoną klasą magazynu identyfikatora — na przykład **`static`** lub **`extern`** — i popraw deklarację do dopasowania.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2071.

```cpp
// C2071.cpp
// compile with: /c
struct C {
   extern int i;   // C2071
};
struct D {
   int i;   // OK, no extern on an automatic
};
```

Poniższy przykład generuje C2071.

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
