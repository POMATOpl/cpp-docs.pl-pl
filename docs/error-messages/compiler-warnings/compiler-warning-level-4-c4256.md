---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4256'
title: Ostrzeżenie kompilatora (poziom 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 3ccd8447f930f40df5e488714cdcfb52e54d9928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189304"
---
# <a name="compiler-warning-level-4-c4256"></a>Ostrzeżenie kompilatora (poziom 4) C4256

"Function": Konstruktor dla klasy z wirtualnymi bazami ma "..."; wywołania mogą nie być zgodne ze starszymi wersjami Visual C++

Możliwa niezgodność.

Spójrz na poniższy przykład kodu. Jeśli definicja konstruktora S2:: S2 (int i,...) została skompilowana przy użyciu wersji kompilatora języka Microsoft C++ przed wersją 7, ale Poniższy przykład jest kompilowany przy użyciu bieżącej wersji, wywołanie konstruktora dla S3 nie działa prawidłowo z powodu zmiany konwencji wywoływania przypadku specjalnego. Jeśli obie zostały skompilowane przy użyciu Visual C++ 6,0, wywołanie nie będzie działało całkowicie w żaden sposób, chyba że żadne parametry nie zostały przesłane dla wielokropka.

Aby usunąć to ostrzeżenie,

1. Nie używaj wielokropka w konstruktorze.

1. Upewnij się, że wszystkie składniki w projekcie zostały skompilowane przy użyciu bieżącej wersji (łącznie z bibliotekami, które mogą definiować lub odwoływać się do tej klasy), a następnie Wyłącz ostrzeżenie przy użyciu dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) .

Poniższy przykład generuje C4256:

```cpp
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```
