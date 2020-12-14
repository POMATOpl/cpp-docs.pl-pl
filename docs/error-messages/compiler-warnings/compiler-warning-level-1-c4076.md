---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4076'
title: Ostrzeżenie kompilatora (poziom 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 0bae49d3af23e499851fbf70fb24fdeb817ee03c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198261"
---
# <a name="compiler-warning-level-1-c4076"></a>Ostrzeżenie kompilatora (poziom 1) C4076

> *modyfikator "Type*": nie może być używany z typem "*TypeName*"

## <a name="remarks"></a>Uwagi

Modyfikator typu, niezależnie od tego, czy jest **`signed`** lub **`unsigned`** , nie może być używany z typem innym niż Integer. *modyfikator typu* jest ignorowany.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4076; Aby rozwiązać ten problem, Usuń **`unsigned`** modyfikator typu:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
