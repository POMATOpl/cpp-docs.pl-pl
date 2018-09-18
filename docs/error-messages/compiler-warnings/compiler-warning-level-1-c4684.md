---
title: Kompilator ostrzeżenie (poziom 1) C4684 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4684
dev_langs:
- C++
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c640239ef0436c6f76e8658fc4dc8a4403418de8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087860"
---
# <a name="compiler-warning-level-1-c4684"></a>Kompilator ostrzeżenie (poziom 1) C4684

"attribute": ostrzeżenie!! atrybut może powodować generowanie nieprawidłowego kodu: Używaj ostrożnie

Użyto atrybutu, który często nie należy używać.

Poniższy przykład spowoduje wygenerowanie C4684:

```
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```