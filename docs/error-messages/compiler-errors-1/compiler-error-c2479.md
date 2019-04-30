---
title: Błąd kompilatora C2479
ms.date: 11/04/2016
f1_keywords:
- C2479
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
ms.openlocfilehash: 8b3b226ccbe42ec88ed92c64b97256d80a983254
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383265"
---
# <a name="compiler-error-c2479"></a>Błąd kompilatora C2479

'Identyfikator': "ALLOCATE()" jest prawidłowy tylko dla elementów danych statycznego obszaru

`__declspec( allocate())` Statycznego tylko do danych można używać składni.

Poniższy przykład spowoduje wygenerowanie C2479:

```
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```