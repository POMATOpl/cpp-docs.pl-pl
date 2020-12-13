---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4625'
title: Ostrzeżenie kompilatora (poziom 4) C4625
ms.date: 11/04/2016
f1_keywords:
- C4625
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
ms.openlocfilehash: 1b154e1f2e52c21affd47c1b0fc30d29b290269e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134228"
---
# <a name="compiler-warning-level-4-c4625"></a>Ostrzeżenie kompilatora (poziom 4) C4625

"Klasa pochodna": Konstruktor kopiujący został niejawnie zdefiniowany jako usunięty, ponieważ Konstruktor kopiujący klasy bazowej jest niedostępny lub usunięty

Konstruktor kopiujący został usunięty lub nie jest dostępny w klasie bazowej i dlatego nie został wygenerowany dla klasy pochodnej. Każda próba skopiowania obiektu tego typu spowoduje błąd kompilatora.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4625 i pokazuje, jak rozwiązać ten problem.

```cpp
// C4625.cpp
// compile with: /W4 /c
#pragma warning(default : 4625)

struct A {
   A() {}

private:
   A(const A&) {}
};

struct C : private virtual A {};
struct B :  C {};   // C4625 no copy constructor

struct D : A {};
struct E :  D {};   // OK
```
