---
title: Błąd kompilatora C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: a2a164f919dc7535a4587d51f4f7dba8653a1760
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214688"
---
# <a name="compiler-error-c2360"></a>Błąd kompilatora C2360

Inicjalizacja elementu "identifier" jest pomijana w etykiecie "Case"

Inicjowanie `identifier` można pominąć w **`switch`** instrukcji. Nie można przeskoczyć do wcześniejszej deklaracji z inicjatorem, chyba że deklaracja jest ujęta w bloku. (Chyba że jest zadeklarowany wewnątrz bloku, zmienna jest w zakresie do końca **`switch`** instrukcji).

Poniższy przykład generuje C2360:

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

Możliwe rozwiązanie:

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
