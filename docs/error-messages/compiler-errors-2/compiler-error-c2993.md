---
description: 'Dowiedz się więcej o: błąd kompilatora C2993'
title: Błąd kompilatora C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 2c43d4f3e54378d419f1945b1f6b38e9ee4d9758
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136425"
---
# <a name="compiler-error-c2993"></a>Błąd kompilatora C2993

"Identyfikator": niedozwolony typ dla parametru szablonu bez typu "parameter"

Nie można zadeklarować szablonu ze strukturą lub argumentem Union. Użyj wskaźników, aby przekazać struktury i związki jako parametry szablonu.

Poniższy przykład generuje C2993:

```cpp
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

Ten błąd zostanie również wygenerowany w wyniku działania kompilatora, który został wykonany w programie Visual Studio .NET 2003: parametry szablonu bez typu zmiennoprzecinkowego nie są już dozwolone. Standard C++ nie zezwala na parametry szablonu bez typu zmiennoprzecinkowego.

Jeśli jest to szablon funkcji, użyj argumentu funkcji, aby przekazać parametr szablonu bez typu zmiennoprzecinkowego (ten kod będzie prawidłowy w wersjach programu Visual Studio .NET 2003 i Visual Studio .NET Visual C++). Jeśli jest to szablon klasy, nie ma żadnego prostego obejścia.

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
