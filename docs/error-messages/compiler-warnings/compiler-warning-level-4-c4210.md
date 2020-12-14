---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4210'
title: Ostrzeżenie kompilatora (poziom 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: aeb64e1f07f82ce1779c58bbacf3b0576642f343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314766"
---
# <a name="compiler-warning-level-4-c4210"></a>Ostrzeżenie kompilatora (poziom 4) C4210

użyto niestandardowego rozszerzenia: zakres funkcji danego pliku

Z domyślnymi rozszerzeniami Microsoft ([/ze](../../build/reference/za-ze-disable-language-extensions.md)), deklaracje funkcji mają zakres pliku.

```c
// C4210.c
// compile with: /W4 /c
void func1()
{
   extern int func2( double );   // C4210 expected
}

int main()
{
   func2( 4 );   //  /Ze passes 4 as type double
}                //  /Za passes 4 as type int
```

To rozszerzenie może uniemożliwić przenośnie kodu do innych kompilatorów.
