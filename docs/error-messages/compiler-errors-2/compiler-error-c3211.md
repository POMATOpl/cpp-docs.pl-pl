---
description: 'Dowiedz się więcej o: błąd kompilatora C3211'
title: Błąd kompilatora C3211
ms.date: 11/04/2016
f1_keywords:
- C3211
helpviewer_keywords:
- C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
ms.openlocfilehash: eaa495c8759194ed89322bd63298ea186057e8c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173860"
---
# <a name="compiler-error-c3211"></a>Błąd kompilatora C3211

"Jawna specjalizacja": Jawna specjalizacja używa składni częściowej specjalizacji, zamiast tego użyj szablonu <> 

Jawna specjalizacja była źle sformułowana.

Poniższy przykład generuje C3211:

```cpp
// C3211.cpp
// compile with: /LD
template<class T>
struct s;

template<class T>
// use the following line instead
// template<>
struct s<int>{};   // C3211
```
