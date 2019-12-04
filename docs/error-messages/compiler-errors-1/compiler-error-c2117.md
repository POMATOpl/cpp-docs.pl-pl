---
title: Błąd kompilatora C2117
ms.date: 11/04/2016
f1_keywords:
- C2117
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
ms.openlocfilehash: 7166ba4e5f3a0fb66360d388fb18367bf553492e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750458"
---
# <a name="compiler-error-c2117"></a>Błąd kompilatora C2117

"Identyfikator": przepełnienie granic tablicy

Tablica ma zbyt wiele inicjatorów:

- Elementy tablicy i inicjatory są niezgodne z rozmiarem i ilością.

- Brak miejsca na terminator o wartości null w ciągu.

Poniższy przykład generuje C2117:

```cpp
// C2117.cpp
int main() {
   char abc[4] = "abcd";   // C2117
   char def[4] = "abd";   // OK
}
```
