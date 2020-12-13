---
description: Dowiedz się więcej na temat:. PUSHREG
title: .PUSHREG
ms.date: 12/16/2019
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: b9316cebad76747c69cb577fcae71f28b6bd9530
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131264"
---
# <a name="pushreg"></a>.PUSHREG

Generuje `UWOP_PUSH_NONVOL` wpis kodu unwind dla określonego numeru rejestru przy użyciu bieżącego przesunięcia w prologu.

## <a name="syntax"></a>Składnia

> . *Rejestr* PUSHREG

## <a name="remarks"></a>Uwagi

**. PUSHREG** ml64.exe umożliwia użytkownikom Określanie, jak działa funkcja ramki, i jest dozwolona tylko w prologu, która rozciąga się od deklaracji **Frame** [proces](proc.md) do [. ENDPROLOG](dot-endprolog.md) . Dyrektywy te nie generują kodu; generują one tylko `.xdata` i `.pdata` . **. PUSHREG** powinien być poprzedzony instrukcjami, które faktycznie implementują akcje, które mają być odwiązane. Dobrym sposobem jest Zawijanie dyrektyw unwind i kodu, które są przeznaczone do odwinięcia w makrze w celu zapewnienia zgody.

*Rejestr* może być jednym z: \
RAX | RCX | RDX | RBX | RDI | RSI | RBP | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15.

Aby uzyskać więcej informacji, zobacz [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Sample

### <a name="description"></a>Opis

Poniższy przykład przedstawia sposób wypychania rejestrów nietrwałych.

### <a name="code"></a>Kod

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

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
