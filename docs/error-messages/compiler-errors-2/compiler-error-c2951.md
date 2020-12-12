---
description: 'Dowiedz się więcej o: błąd kompilatora C2951'
title: Błąd kompilatora C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: 7f3030764cdd36d40fbd78a8c3768c7dc1085c21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322110"
---
# <a name="compiler-error-c2951"></a>Błąd kompilatora C2951

Deklaracje typów są dozwolone tylko w globalnym, przestrzeni nazw lub zakresie klasy

Nie można zadeklarować klasy generycznej lub szablonu poza zakresem globalnym lub przestrzeni nazw. W przypadku stosowania deklaracji ogólnych lub szablonów w pliku dołączanym upewnij się, że plik dołączany jest w zakresie globalnym.

Poniższy przykład generuje C2951:

```cpp
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```
