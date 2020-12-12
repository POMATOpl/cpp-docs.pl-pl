---
description: 'Dowiedz się więcej o: błąd kompilatora C2892'
title: Błąd kompilatora C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: bcc1a43298973e270c39656b965b76cd75f3472e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278353"
---
# <a name="compiler-error-c2892"></a>Błąd kompilatora C2892

lokalna Klasa nie powinna mieć szablonów składowych

Funkcje składowe z szablonu są nieprawidłowe w klasie, która jest zdefiniowana w funkcji.

Poniższy przykład generuje C2892:

```cpp
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```
