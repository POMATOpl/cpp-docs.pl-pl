---
description: 'Dowiedz się więcej o: PROC'
title: PROC
ms.date: 12/06/2019
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: fe811ed1723dc1a41014720d97b6f21ab596c2e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97126038"
---
# <a name="proc"></a>PROC

Oznacza początek i koniec bloku procedury o nazwie *Label*. Instrukcje w bloku mogą być wywoływane przy użyciu instrukcji **call** lub [Invoke](invoke.md) dyrektywy.

## <a name="syntax"></a>Składnia

> *etykieta* **proc** ⟦*Distance*⟧ ⟦*Language-Type*⟧ ⟦ **Public**  |  **Private**  |  **Export** ⟧ ⟦ __\<__*prologuearg*__>__ ⟧ ⟦**używa** *reglist*⟧ ⟦__,__ *Parameter* ⟦__:__*tag*⟧... ⟧\
> ⟦**Frame** ⟦__:__*ehandler-Address*⟧ ⟧ \
> *zatwierdzeni*\
> *etykieta* **ENDP**

## <a name="remarks"></a>Uwagi

Argumenty *⟧ ⟦**odległości*⟧ i ⟦ są prawidłowe tylko w 32-bitowym MASM.

⟦**Frame** ⟦__:__*ehandler-Address*⟧ ⟧ jest prawidłowa tylko z ml64.exe i powoduje, że program MASM generuje wpis tabeli funkcji w. pdata i unwind Information in. xdata dla zachowania funkcji unwind dla wyjątku strukturalnego.

Gdy atrybut **Frame** jest używany, musi następować po nim [. ENDPROLOG](dot-endprolog.md) .

Aby uzyskać więcej informacji na temat używania ml64.exe, zobacz [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md) .

## <a name="example"></a>Przykład

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

Powyższy kod emituje następującą tabelę funkcji i informacje o rozwinięcia:

```Output
FileHeader->Machine 34404
Dumping Unwind Information for file ex2.exe

.pdata entry 1 0x00001000 0x00001023

  Unwind data: 0x00002000

    Unwind version: 1
    Unwind Flags: None
    Size of prologue: 0x08
    Count of codes: 3
    Frame register: rbp
    Frame offset: 0x0
    Unwind codes:

      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00
      Code offset: 0x05, ALLOC_SMALL, size=0x10
      Code offset: 0x01, PUSH_NONVOL, register=rbp
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
