---
description: 'Dowiedz się więcej o: błąd kompilatora C2870'
title: Błąd kompilatora C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 74e7f2de5cfbb5aca6bd653f5711b989de4ef326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333766"
---
# <a name="compiler-error-c2870"></a>Błąd kompilatora C2870

"name": definicja przestrzeni nazw musi znajdować się w zakresie pliku lub bezpośrednio w innej definicji przestrzeni nazw

Nieprawidłowo zdefiniowana przestrzeń nazw `name` . Przestrzenie nazw muszą być zdefiniowane w zakresie pliku (poza wszystkimi blokami i klasami) lub bezpośrednio w innej przestrzeni nazw.

Poniższy przykład generuje C2870:

```cpp
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```
