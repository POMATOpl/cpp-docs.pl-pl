---
title: Błąd kompilatora C2688 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2688
dev_langs:
- C++
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 729cedf532621bf9c65014cb8d92f3a262f399fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033099"
---
# <a name="compiler-error-c2688"></a>Błąd kompilatora C2688

"C2::fgrv": kowariantne zwracane z wielokrontym lub wirtualnym dziedziczeniem nie są obsługiwane przez funkcję VarArgs

Kowariantne typy zwracane nie są obsługiwane w programie Visual C++, gdy funkcja zawiera zmienne argumenty.

Aby rozwiązać ten problem, zdefiniuj funkcji tak, aby nie używać argumentów zmiennych lub wprowadzić wartości zwracane takie same dla wszystkich funkcji wirtualnych.

Poniższy przykład spowoduje wygenerowanie C2688:

```
// C2688.cpp
struct G1 {};
struct G2 {};
struct G3 : G1, G2 {};
struct G4 {};
struct G5 {};
struct G6 : G4, G5 {};
struct G7 : G3, G6 {};

struct C1 {
   virtual G4& fgrv(int,...);
};

struct C2 : C1 {
   virtual G7& fgrv(int,...);   // C2688, does not return G4&
};
```