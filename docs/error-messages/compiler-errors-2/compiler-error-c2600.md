---
description: 'Dowiedz się więcej o: błąd kompilatora C2600'
title: Błąd kompilatora C2600
ms.date: 11/04/2016
f1_keywords:
- C2600
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
ms.openlocfilehash: fbd99cb50bc3afc748e1d3b2e954c584a7cef78b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120025"
---
# <a name="compiler-error-c2600"></a>Błąd kompilatora C2600

"Function": nie można zdefiniować wygenerowanej przez kompilator specjalnej funkcji składowej (musi być najpierw zadeklarowana w klasie)

Zanim funkcje członkowskie, takie jak konstruktory lub destruktory, można zdefiniować dla klasy, muszą one być zadeklarowane w klasie. Kompilator może generować domyślne konstruktory i destruktory (o nazwie specjalne funkcje członkowskie), jeśli żadna z nich nie jest zadeklarowana w klasie. Jeśli jednak zdefiniujesz jedną z tych funkcji bez zgodnej deklaracji w klasie, kompilator wykryje konflikt.

Aby naprawić ten błąd, w deklaracji klasy Zadeklaruj każdą funkcję członkowską, która została zdefiniowana poza deklaracją klasy.

Poniższy przykład generuje C2600:

```cpp
// C2600.cpp
// compile with: /c
class C {};
C::~C() {}   // C2600

class D {
   D::~D();
};

D::~D() {}
```
