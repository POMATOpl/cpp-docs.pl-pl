---
description: 'Dowiedz się więcej o: błąd kompilatora C2695'
title: Błąd kompilatora C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6137749725de5c2285cb5defd84fd7c8c0f2e237
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326646"
---
# <a name="compiler-error-c2695"></a>Błąd kompilatora C2695

"function1": przesłanianie wirtualnej funkcji różni się od "function2" tylko konwencją wywoływania

Sygnatura funkcji w klasie pochodnej nie może przesłonić funkcji w klasie bazowej i zmienić konwencji wywoływania.

Poniższy przykład generuje C2695:

```cpp
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```
