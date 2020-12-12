---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4538'
title: Ostrzeżenie kompilatora (poziom 3) C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: 4f5d6ee8b6144db4fad519f1484d00fe325591a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257852"
---
# <a name="compiler-warning-level-3-c4538"></a>Ostrzeżenie kompilatora (poziom 3) C4538

"Type": kwalifikatory const/volatile dla tego typu nie są obsługiwane

Słowo kluczowe kwalifikatora zostało nieprawidłowo zastosowane do tablicy. Aby uzyskać więcej informacji, zobacz [Array](../../extensions/arrays-cpp-component-extensions.md).

Poniższy przykład generuje C4538:

```cpp
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```
