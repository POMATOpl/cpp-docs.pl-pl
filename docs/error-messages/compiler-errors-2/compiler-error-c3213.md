---
description: 'Dowiedz się więcej o: błąd kompilatora C3213'
title: Błąd kompilatora C3213
ms.date: 11/04/2016
f1_keywords:
- C3213
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
ms.openlocfilehash: 5ae16ffd94c6d300956bb2723ccbe8c16b0d6b3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291769"
---
# <a name="compiler-error-c3213"></a>Błąd kompilatora C3213

Klasa bazowa "base_type" jest mniej dostępna niż "derived_type"

Typ, który będzie widoczny z zestawu, musi używać publicznie widocznych klas podstawowych.

Poniższy przykład generuje C3213:

```cpp
// C3213.cpp
// compile with: /clr
private ref struct privateG {
public:
   int i;
};

public ref struct publicG {
public:
   int i;
};

public ref struct V : public privateG {   // C3213
public:
   int j;
};

public ref struct W: public publicG {   // OK
public:
   int j;
};
```
