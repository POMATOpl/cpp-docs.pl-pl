---
description: 'Dowiedz się więcej o: błąd kompilatora C2593'
title: Błąd kompilatora C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: 849cd79b1d469d957cf1bde499ce66bd54a64074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120168"
---
# <a name="compiler-error-c2593"></a>Błąd kompilatora C2593

"Identyfikator operatora" jest niejednoznaczny

Zdefiniowano więcej niż jeden możliwy operator dla przeciążonego operatora.

Ten błąd może zostać naprawiony, jeśli używasz jawnego rzutowania dla co najmniej jednego rzeczywistego parametru.

Poniższy przykład generuje C2593:

```cpp
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

Ten błąd może być spowodowany serializacji zmiennej zmiennoprzecinkowej przy użyciu `CArchive` obiektu. Kompilator identyfikuje `<<` operatora jako niejednoznaczny. Jedyne pierwotne typy C++, które `CArchive` mogą serializować, to typy o stałym rozmiarze `BYTE` ,, `WORD` `DWORD` i `LONG` . Wszystkie typy całkowite muszą być rzutowane na jeden z tych typów do serializacji. Typy zmiennoprzecinkowe muszą być archiwizowane przy użyciu `CArchive::Write()` funkcji składowej.

Poniższy przykład pokazuje, jak zarchiwizować zmienną zmiennoprzecinkową ( `f` ) w celu archiwizacji `ar` :

```
ar.Write(&f, sizeof( float ));
```
