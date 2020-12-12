---
description: 'Dowiedz się więcej o: błąd kompilatora C2228'
title: Błąd kompilatora C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 8bf5c4af88f77237699baae5e7a458fca971f126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195063"
---
# <a name="compiler-error-c2228"></a>Błąd kompilatora C2228

po lewej ". identyfikator" musi być klasą/strukturą/Unią

Operand z lewej strony kropki (.) nie jest klasą, strukturą ani Unią.

Poniższy przykład generuje C2228:

```cpp
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

Ten błąd zostanie również wyświetlony, jeśli podczas korzystania z rozszerzeń zarządzanych użyto nieprawidłowej składni. W innych językach programu Visual Studio można użyć operatora kropki w celu uzyskania dostępu do elementu członkowskiego klasy zarządzanej, wskaźnika do obiektu w języku C++, aby uzyskać dostęp do elementu członkowskiego za pomocą operatora->:

Odpowiednich `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

Kliknij `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
