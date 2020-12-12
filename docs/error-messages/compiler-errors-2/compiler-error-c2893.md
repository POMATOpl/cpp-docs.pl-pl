---
description: 'Dowiedz się więcej o: błąd kompilatora C2893'
title: Błąd kompilatora C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: 42e31327096a539feeb691c698b52f57ecb615a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278262"
---
# <a name="compiler-error-c2893"></a>Błąd kompilatora C2893

Nie powiodła się specjalizacja szablonu funkcji "Nazwa szablonu"

Kompilator nie może przeprowadzić specjalizacji szablonu funkcji. Może istnieć wiele przyczyn tego błędu.

Ogólnie rzecz biorąc, metoda rozwiązywania błędu C2893 polega na przejrzeniu podpisu funkcji i upewnieniu się, że można utworzyć wystąpienie każdego typu.

## <a name="example"></a>Przykład

C2893 występuje `f` , ponieważ parametr szablonu `T` jest wywnioskowany jako `std::map<int,int>` , ale nie `std::map<int,int>` ma żadnego elementu członkowskiego `data_type` ( `T::data_type` nie można utworzyć wystąpienia z `T = std::map<int,int>` .). Poniższy przykład generuje C2893.

```cpp
// C2893.cpp
// compile with: /c /EHsc
#include<map>
using namespace std;
class MyClass {};

template<class T>
inline typename T::data_type
// try the following line instead
// inline typename  T::mapped_type
f(T const& p1, MyClass const& p2);

template<class T>
void bar(T const& p1) {
    MyClass r;
    f(p1,r);   // C2893
}

int main() {
   map<int,int> m;
   bar(m);
}
```
