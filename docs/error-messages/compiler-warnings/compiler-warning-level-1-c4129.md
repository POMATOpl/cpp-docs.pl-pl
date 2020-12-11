---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4129'
title: Ostrzeżenie kompilatora (poziom 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: 27ae487016a5d9a60a95e4715261ec5ba9171db4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155283"
---
# <a name="compiler-warning-level-1-c4129"></a>Ostrzeżenie kompilatora (poziom 1) C4129

"Character": nierozpoznany znak sekwencji ucieczki

`character`Następujący ukośnik odwrotny ( \\ ) w znaku lub stałej ciągu nie jest rozpoznawany jako prawidłowa sekwencja ucieczki. Ukośnik odwrotny jest ignorowany i nie jest drukowany. Zostanie wydrukowany znak następujący po ukośniku odwrotnym.

Aby wydrukować pojedynczy ukośnik odwrotny, określ podwójny ukośnik odwrotny ( \\ \\ ).

Standard C++, w sekcji 2.13.2, omawia sekwencje unikowe.

Poniższy przykład generuje C4129:

```cpp
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```
