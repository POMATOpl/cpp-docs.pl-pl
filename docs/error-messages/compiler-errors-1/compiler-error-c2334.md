---
title: Błąd kompilatora C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: 4f068792193fd22ccddc39f9afc555e7c8672d8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188372"
---
# <a name="compiler-error-c2334"></a>Błąd kompilatora C2334

Nieoczekiwany(e) token(y) poprzedzającego ': lub {"; Pomijanie treści widocznych funkcji

Poniższy przykład spowoduje wygenerowanie C2334. Ten błąd występuje po błędzie C2059:

```
// C2334.cpp
// compile with: /c
// C2059 expected
struct s1 {
   s1   {}   // C2334
   s1() {}   // OK
};
```