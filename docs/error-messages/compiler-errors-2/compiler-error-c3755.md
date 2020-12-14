---
description: 'Dowiedz się więcej o: błąd kompilatora C3755'
title: Błąd kompilatora C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 24d6af223b6a15cbf1740bf67144250007c2091d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253588"
---
# <a name="compiler-error-c3755"></a>Błąd kompilatora C3755

"delegat": delegat nie może być zdefiniowany

[Delegat (C++ Component Extensions)](../../extensions/delegate-cpp-component-extensions.md) może być zadeklarowany, ale nie zdefiniowany.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3755.

```cpp
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

C3755 może również wystąpić w przypadku próby utworzenia szablonu delegowania. Poniższy przykład generuje C3755.

```cpp
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```
