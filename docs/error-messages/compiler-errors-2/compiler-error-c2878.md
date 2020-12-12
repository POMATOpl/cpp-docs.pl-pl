---
description: 'Dowiedz się więcej o: błąd kompilatora C2878'
title: Błąd kompilatora C2878
ms.date: 11/04/2016
f1_keywords:
- C2878
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
ms.openlocfilehash: df79869572117eed851c5edd63f94234555cb990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320476"
---
# <a name="compiler-error-c2878"></a>Błąd kompilatora C2878

"name": przestrzeń nazw lub Klasa o tej nazwie nie istnieje

Wprowadzono odwołanie do przestrzeni nazw lub klasy, która nie została zdefiniowana.

Poniższy przykład generuje C2878:

```cpp
// C2878.cpp
// compile with: /c
namespace A {}
namespace B = C;   // C2878 namespace C doesn't exist
namespace B = A;
```
