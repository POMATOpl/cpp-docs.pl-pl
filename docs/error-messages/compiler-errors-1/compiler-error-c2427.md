---
description: 'Dowiedz się więcej o: błąd kompilatora C2427'
title: Błąd kompilatora C2427
ms.date: 11/04/2016
f1_keywords:
- C2427
helpviewer_keywords:
- C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
ms.openlocfilehash: ae1131eb511d9d3f1affad56b576cebd19cb5213
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190175"
---
# <a name="compiler-error-c2427"></a>Błąd kompilatora C2427

"Class": nie można zdefiniować klasy w tym zakresie

Podjęto próbę zdefiniowania klasy zagnieżdżonej, ale Klasa zagnieżdżona jest składową klasy bazowej, a nie z klasą najbardziej zawierającą.

Poniższy przykład generuje C2427:

```cpp
// C2427.cpp
// compile with: /c
template <class T>
struct S {
   struct Inner;
};

struct Y : S<int> {};

struct Y::Inner {};   // C2427

// OK
template<typename T>
struct S<T>::Inner {};
```
