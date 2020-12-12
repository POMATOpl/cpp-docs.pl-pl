---
description: 'Dowiedz się więcej o: błąd kompilatora C3227'
title: Błąd kompilatora C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: 26d66bf3e0c3bc3a6f391d66608f3e6790b2d11d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304145"
---
# <a name="compiler-error-c3227"></a>Błąd kompilatora C3227

"parameter": nie można użyć słowa kluczowego "Keyword" do przydzielenia typu ogólnego

Aby utworzyć wystąpienie typu, wymagany jest odpowiedni Konstruktor. Jednak kompilator nie jest w stanie zapewnić, że jest dostępny odpowiedni Konstruktor.

Aby rozwiązać ten problem, można użyć szablonów zamiast typów ogólnych lub użyć jednej z kilku metod tworzenia wystąpienia typu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3227.

```cpp
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```
