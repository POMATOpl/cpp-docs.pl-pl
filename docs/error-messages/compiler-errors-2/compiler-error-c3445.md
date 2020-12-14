---
description: 'Dowiedz się więcej o: błąd kompilatora C3445'
title: Błąd kompilatora C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 992c0e4f6e8b068bf6c038a6a5f58b45dd80a3c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316039"
---
# <a name="compiler-error-c3445"></a>Błąd kompilatora C3445

> podczas inicjowania listy *typu "Type*" nie można używać konstruktora jawnego

Zgodnie ze standardem ISO C++ 17, kompilator jest wymagany do rozważania jawnego konstruktora w celu rozpoznania przeciążenia w ramach inicjalizacji listy kopiowania, ale musi zgłosić błąd, jeśli to przeciążenie jest rzeczywiście wybrane.

Począwszy od programu Visual Studio 2017, kompilator wyszukuje błędy związane z tworzeniem obiektów przy użyciu listy inicjatorów, która nie została znaleziona przez program Visual Studio 2015. Te błędy mogą prowadzić do awarii lub niezdefiniowanego zachowania w czasie wykonywania.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3445.

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

Aby poprawić ten błąd, należy zamiast tego użyć inicjowania bezpośredniego:

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```
