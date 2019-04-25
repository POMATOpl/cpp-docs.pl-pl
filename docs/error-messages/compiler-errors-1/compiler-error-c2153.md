---
title: Błąd kompilatora C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: eeb7da509ffb1b8c408763c79d471586eb94f383
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175163"
---
# <a name="compiler-error-c2153"></a>Błąd kompilatora C2153

stałe szesnastkowe muszą mieć co najmniej jedną cyfrę szesnastkową

Stałe szesnastkowe 0 x 0 X i \x nie są prawidłowe. Należy wykonać co najmniej jedną cyfrę szesnastkową x lub X.

Poniższy przykład spowoduje wygenerowanie C2153:

```
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```