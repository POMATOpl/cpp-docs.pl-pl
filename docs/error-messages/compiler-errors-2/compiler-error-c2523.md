---
description: 'Dowiedz się więcej o: błąd kompilatora C2523'
title: Błąd kompilatora C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: c9907742903cf4c13364d6ac63bb561b52e02232
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151167"
---
# <a name="compiler-error-c2523"></a>Błąd kompilatora C2523

"Class:: ~ identifier": niezgodność tagów destruktora/finalizatora

Nazwa destruktora musi być nazwą klasy poprzedzoną tyldą ( `~` ). Konstruktor i destruktor są jedynymi elementami członkowskimi, które mają taką samą nazwę jak Klasa.

Poniższy przykład generuje C2523:

```cpp
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```
