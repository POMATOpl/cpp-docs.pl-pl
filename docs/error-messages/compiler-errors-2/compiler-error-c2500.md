---
description: 'Dowiedz się więcej o: błąd kompilatora od C2500'
title: Błąd kompilatora od C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: 39d1ab0876470b443d4444a3c583cc0993c98325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275974"
---
# <a name="compiler-error-c2500"></a>Błąd kompilatora od C2500

"Identifier1": "identifier2" jest już bezpośrednią klasą bazową

Klasa lub struktura pojawia się więcej niż jeden raz na liście klas bazowych.

Baza bezpośrednia jest wymieniona na liście podstawowej. Baza pośrednia jest klasą bazową jednej z klas na liście podstawowej.

Nie można określić klasy jako bezpośredniej klasy bazowej więcej niż raz. Klasy można użyć jako pośredniej klasy bazowej więcej niż raz.

Poniższy przykład generuje od C2500:

```cpp
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```
