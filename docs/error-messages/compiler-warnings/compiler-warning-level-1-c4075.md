---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4075'
title: Ostrzeżenie kompilatora (poziom 1) C4075
ms.date: 11/04/2016
f1_keywords:
- C4075
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
ms.openlocfilehash: 86937dcbb527b9fed46209d7438cc782714e89af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198274"
---
# <a name="compiler-warning-level-1-c4075"></a>Ostrzeżenie kompilatora (poziom 1) C4075

inicjatory są umieszczane w nierozpoznanym obszarze inicjalizacji

[Init_seg #pragma](../../preprocessor/init-seg.md) używa nierozpoznanej nazwy sekcji. Kompilator ignoruje polecenie **pragma** .

Poniższy przykład generuje C4075:

```cpp
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```
