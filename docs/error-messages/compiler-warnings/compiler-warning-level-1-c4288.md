---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4288'
title: Ostrzeżenie kompilatora (poziom 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: 827dd357aa4504c9f806cbcbe534ae45ccaf33b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311724"
---
# <a name="compiler-warning-level-1-c4288"></a>Ostrzeżenie kompilatora (poziom 1) C4288

> użyto niestandardowego rozszerzenia: "var": Zmienna sterująca pętli zadeklarowana w pętli for jest używana poza zakresem pętli for; powoduje konflikt z deklaracją w zewnętrznym zakresie

Podczas kompilowania z [`/Ze`](../../build/reference/za-ze-disable-language-extensions.md) i **/Zc: forScope-**, zmienna zadeklarowana w **`for`** pętli została użyta po zakresie pętli [for](../../cpp/for-statement-cpp.md). Rozszerzenie firmy Microsoft do języka C++ umożliwia tej zmiennej pozostawienie w zakresie, a C4288 przypomina o tym, że pierwsza deklaracja zmiennej nie jest używana.

Zobacz [`/Zc:forScope`](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) , aby uzyskać informacje na temat sposobu określania rozszerzenia firmy Microsoft w **`for`** pętlach with/ze.

Poniższy przykład generuje C4288:

```cpp
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```
