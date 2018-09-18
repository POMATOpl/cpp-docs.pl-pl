---
title: Błąd kompilatora C3211 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3211
dev_langs:
- C++
helpviewer_keywords:
- C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ed045d1941db85bf0c1a8bbf8d94bf0c9c08ed6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043433"
---
# <a name="compiler-error-c3211"></a>Błąd kompilatora C3211

"jawna specjalizacja": jawna specjalizacja używa składni częściowej specjalizacji, zamiast tego użyj <> szablonu

Jawna specjalizacja został niewłaściwie sformatowany.

Poniższy przykład spowoduje wygenerowanie C3211:

```
// C3211.cpp
// compile with: /LD
template<class T>
struct s;

template<class T>
// use the following line instead
// template<>
struct s<int>{};   // C3211
```