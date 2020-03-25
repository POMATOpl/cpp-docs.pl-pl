---
title: Ostrzeżenie kompilatora (poziom 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: e37ff1fbcfd2ad4088a94204374b33c2c103797c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161324"
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
