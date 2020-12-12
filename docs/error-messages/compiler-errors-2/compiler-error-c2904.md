---
description: 'Dowiedz się więcej o: błąd kompilatora C2904'
title: Błąd kompilatora C2904
ms.date: 11/04/2016
f1_keywords:
- C2904
helpviewer_keywords:
- C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
ms.openlocfilehash: f49ff355a69fd0487e10de088e9a676f4b6981af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270696"
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
