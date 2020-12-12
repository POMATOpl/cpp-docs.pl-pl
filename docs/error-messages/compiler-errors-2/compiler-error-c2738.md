---
description: 'Dowiedz się więcej o: błąd kompilatora C2738'
title: Błąd kompilatora C2738
ms.date: 11/04/2016
f1_keywords:
- C2738
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
ms.openlocfilehash: 80d56a4491cf6205313b4da66cb695b956cb60a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123100"
---
# <a name="compiler-error-c2738"></a>Błąd kompilatora C2738

"Deklaracja": jest niejednoznaczna lub nie jest składową elementu "Type"

Funkcja została zadeklarowana nieprawidłowo.

Poniższy przykład generuje C2738:

```cpp
// C2738.cpp
struct A {
   template <class T> operator T*();
   // template <class T> operator T();
};

template <>
A::operator int() {   // C2738

// try the following line instead
// A::operator int*() {

// or use the commented member declaration

   return 0;
}
```
