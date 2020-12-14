---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4937'
title: Ostrzeżenie kompilatora (poziom 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: fa614e9f93cf83afbe3ff46e624f13b5199a28d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251248"
---
# <a name="compiler-warning-level-4-c4937"></a>Ostrzeżenie kompilatora (poziom 4) C4937

"Tekst1" i "Tekst2" są nierozróżniane jako argumenty dyrektywy "

Ze względu na sposób, w jaki kompilator przetwarza argumenty do dyrektyw, nazwy, które mają znaczenie dla kompilatora, takie jak słowa kluczowe z wieloma reprezentacjami tekstowymi (Formularze z pojedynczym i podwójnym podkreśleniem), nie można wyróżnić.

Przykładami takich ciągów są __cdecl i \_ _forceinline.  Uwaga w obszarze/za są włączone tylko formularze podwójnego podkreślenia.

Poniższy przykład generuje C4937:

```cpp
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```
