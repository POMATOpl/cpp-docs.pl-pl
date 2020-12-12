---
description: 'Dowiedz się więcej na temat: wywoływanie funkcji C w zestawie wbudowanym'
title: Wywoływanie funkcji C w asemblerze wbudowanym
ms.date: 08/30/2018
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
ms.openlocfilehash: 5cdace4a909cbc49567988f85085eed5d84eadf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117994"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Wywoływanie funkcji C w asemblerze wbudowanym

**Specyficzne dla firmy Microsoft**

**`__asm`** Blok może wywoływać funkcje języka c, w tym procedury biblioteki języka c. Poniższy przykład wywołuje `printf` procedurę biblioteki:

```cpp
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp
// processor: x86
#include <stdio.h>

char format[] = "%s %s\n";
char hello[] = "Hello";
char world[] = "world";
int main( void )
{
   __asm
   {
      mov  eax, offset world
      push eax
      mov  eax, offset hello
      push eax
      mov  eax, offset format
      push eax
      call printf
      //clean up the stack so that main can exit cleanly
      //use the unused register ebx to do the cleanup
      pop  ebx
      pop  ebx
      pop  ebx
   }
}
```

Ponieważ argumenty funkcji są przekazywane na stosie, po prostu wypchnij potrzebne argumenty — wskaźniki ciągu, w poprzednim przykładzie — przed wywołaniem funkcji. Argumenty są wypychane w odwrotnej kolejności, dlatego są wychodzące ze stosu w odpowiedniej kolejności. Aby emulować instrukcję języka C

```cpp
printf( format, hello, world );
```

przykład wypchnięcie wskaźników do `world` , `hello` , i `format` , w tej kolejności, a następnie wywołuje `printf` .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Asembler wbudowany](../../assembler/inline/inline-assembler.md)<br/>
