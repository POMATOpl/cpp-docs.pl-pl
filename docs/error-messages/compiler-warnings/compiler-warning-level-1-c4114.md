---
title: Ostrzeżenie kompilatora (poziom 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 8d2b0339ff3cce9a68dce57a5f2b4efac076c5c2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233317"
---
# <a name="compiler-warning-level-1-c4114"></a>Ostrzeżenie kompilatora (poziom 1) C4114

kwalifikator tego samego typu użyty więcej niż raz

Deklaracja typu lub definicja używa kwalifikatora typu ( **`const`** , **`volatile`** , **`signed`** lub **`unsigned`** ) więcej niż raz. Powoduje to ostrzeżenie z rozszerzeniami firmy Microsoft (/ze) i błędem zgodnym ze standardem ANSI (/za).

Poniższy przykład generuje C4114:

```cpp
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

Poniższy przykład generuje C4114:

```cpp
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
