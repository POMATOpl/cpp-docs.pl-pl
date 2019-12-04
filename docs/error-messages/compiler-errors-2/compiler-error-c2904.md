---
title: Błąd kompilatora C2904
ms.date: 11/04/2016
f1_keywords:
- C2904
helpviewer_keywords:
- C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
ms.openlocfilehash: 506618da12af7d78db948f1a4197bf93367b7f7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750602"
---
# <a name="compiler-error-c2904"></a>Błąd kompilatora C2904

"Identyfikator": nazwa już używana dla szablonu w bieżącym zakresie

Sprawdź kod dla zduplikowanych nazw.

Poniższy przykład generuje C2904:

```cpp
// C2904.cpp
// compile with: /c
void X();  // X is declared as a function
template<class T> class X{};  // C2904
```
