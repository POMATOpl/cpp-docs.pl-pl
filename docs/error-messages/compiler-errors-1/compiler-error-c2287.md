---
description: 'Dowiedz się więcej o: błąd kompilatora C2287'
title: Błąd kompilatora C2287
ms.date: 11/04/2016
f1_keywords:
- C2287
helpviewer_keywords:
- C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
ms.openlocfilehash: 00a99ee553b4afc86a49ce80c61f2733c70b716f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124049"
---
# <a name="compiler-error-c2287"></a>Błąd kompilatora C2287

"Klasa": reprezentacja dziedziczenia: wartość "representation1" jest mniej ogólna niż wymagana wartość "representation2"

Klasa jest zadeklarowana z prostszym reprezentacją niż jest to wymagane.

Poniższy przykład generuje C2287:

```cpp
// C2287.cpp
// compile with: /vmg /c
class __single_inheritance X;
class __single_inheritance Y;

struct A { };
struct B { };
struct X : A, B { };  // C2287  X uses multiple inheritance
struct Y : A { };  // OK
```
