---
description: 'Dowiedz się więcej o: błąd kompilatora C2912'
title: Błąd kompilatora C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: 405c4acb5da6aa83e4b5d45e2297f1259a0d932e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270527"
---
# <a name="compiler-error-c2912"></a>Błąd kompilatora C2912

Jawna specjalizacja "Deklaracja" nie jest specjalizacją szablonu funkcji

Nie można specjalizacji funkcji niebędącej szablonem.

Poniższy przykład generuje C2912:

```cpp
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

Ten błąd zostanie również wygenerowany w wyniku działania kompilatora, który został wykonany w programie Visual Studio .NET 2003: dla każdej jawnej specjalizacji należy wybrać parametry jawnej specjalizacji, na przykład te, które pasują do parametrów szablonu podstawowego.

```cpp
// C2912b.cpp
class CF {
public:
   template <class A> CF(const A& a) {}   // primary template

   // attempted explicit specialization
   template <> CF(const char* p) {}   // C2912

   // try the following line instead
   // template <> CF(const char& p) {}
};
```
