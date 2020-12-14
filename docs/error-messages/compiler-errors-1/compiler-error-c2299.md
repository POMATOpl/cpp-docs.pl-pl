---
description: 'Dowiedz się więcej o: błąd kompilatora C2299'
title: Błąd kompilatora C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: eb96829c4e16153a0a304a5b2a9640d4591dec3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235102"
---
# <a name="compiler-error-c2299"></a>Błąd kompilatora C2299

"Function": zmiana zachowania: Jawna specjalizacja nie może być konstruktorem kopiującym ani operatorem przypisania kopiowania

Ten błąd może być również wygenerowany jako wynik zgodności kompilatora, który został wykonany dla programu Visual Studio 2005: poprzednie wersje Visual C++ dozwolone jawne specjalizacje dla konstruktora kopiującego lub operatora przypisania kopiowania.

Aby rozwiązać C2299, nie należy tworzyć konstruktora kopiującego ani operatora przypisania jako funkcji szablonu, ale raczej nie jest funkcją szablonu, która przyjmuje typ klasy. Każdy kod, który wywołuje Konstruktor kopiujący lub operator przypisania przez jawne określenie argumentów szablonu, musi usunąć argumenty szablonu.

Poniższy przykład generuje C2299:

```cpp
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```
