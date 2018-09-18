---
title: Kompilator ostrzeżenie (poziom 4) C4389 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4389
dev_langs:
- C++
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68d67ae253926e79b6bc13d339ac303cca767090
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022568"
---
# <a name="compiler-warning-level-4-c4389"></a>Kompilator ostrzeżenie (poziom 4) C4389

'operator': niezgodność ze znakiem/bez znaku

Operację zaangażowany zmienne znakiem i bez znaku. Może to spowodować utratę danych.

Poniższy przykład spowoduje wygenerowanie C4389:

```
// C4389.cpp
// compile with: /W4
#pragma warning(default: 4389)

int main()
{
   int a = 9;
   unsigned int b = 10;
   if (a == b)   // C4389
      return 0;
   else
      return 0;
};
```