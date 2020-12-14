---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4429'
title: Ostrzeżenie kompilatora (poziom 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: dbd552eb2f8e021f8bf7b7747e2a8aee49bb05a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241368"
---
# <a name="compiler-warning-level-4-c4429"></a>Ostrzeżenie kompilatora (poziom 4) C4429

możliwa niekompletna lub nieprawidłowo sformułowana nazwa znaku uniwersalnego

Kompilator wykrył sekwencję znaków, która może być błędnie sformatowaną nazwą znaku uniwersalnego. Po nazwie uniwersalnego znaku `\u` następuje cztery cyfry szesnastkowe, `\U` po których następuje osiem cyfr szesnastkowych.

Poniższy przykład generuje C4429:

```cpp
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```
