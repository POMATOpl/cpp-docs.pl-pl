---
title: Błąd kompilatora C2117
ms.date: 11/04/2016
f1_keywords:
- C2117
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
ms.openlocfilehash: 2f6a1e26972f093e50c5e655935f750195ab7d3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338574"
---
# <a name="compiler-error-c2117"></a>Błąd kompilatora C2117

'Identyfikator': przepełnienie granic tablicy

Tablica ma zbyt wiele inicjatorów:

- Inicjatory i elementy tablicy nie są zgodne rozmiaru i liczby.

- Nie miejsca dla terminator o wartości null w ciągu.

Poniższy przykład spowoduje wygenerowanie C2117:

```
// C2117.cpp
int main() {
   char abc[4] = "abcd";   // C2117
   char def[4] = "abd";   // OK
}
```