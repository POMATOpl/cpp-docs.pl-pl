---
description: 'Dowiedz się więcej o: błąd kompilatora C2378'
title: Błąd kompilatora C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: 2a608cf2aa031da26356ec1b2643fc033ff9ddf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174731"
---
# <a name="compiler-error-c2378"></a>Błąd kompilatora C2378

"Identyfikator": zmiana definicji; symbol nie może być przeciążony przy użyciu elementu typedef

Identyfikator został ponownie zdefiniowany jako **`typedef`** .

Poniższy przykład generuje C2378:

```cpp
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```
