---
description: 'Dowiedz się więcej o: błąd kompilatora C2553'
title: Błąd kompilatora C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 5f5e3eb9d94935aa8e6974f72517e7193ba07db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134501"
---
# <a name="compiler-error-c2553"></a>Błąd kompilatora C2553

"base_function": przesłanianie typu zwracanego funkcji wirtualnej różni się od "override_function"

Funkcja w klasie pochodnej próbowała zastąpić funkcję wirtualną w klasie bazowej, ale funkcja klasy pochodnej nie ma tego samego typu zwracanego co funkcja klasy bazowej.  Sygnatura funkcji przesłaniania musi być zgodna z sygnaturą zastępowanej funkcji.

Poniższy przykład generuje C2553:

```cpp
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```
