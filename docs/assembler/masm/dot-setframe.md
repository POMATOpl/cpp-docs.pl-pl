---
description: Dowiedz się więcej na temat:. SETFRAME
title: .SETFRAME
ms.date: 12/17/2019
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: b3554da14344293f00c499bc3084e6ddfd93c2ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131082"
---
# <a name="setframe"></a>.SETFRAME

Wypełnia pole rejestr ramek i przesunięcia w informacjach o rozwinięcia przy użyciu określonego rejestru (*reg*) i przesunięcia (*przesunięcie*). Przesunięcie musi być wielokrotnością 16 i mniejszą lub równą 240. Ta dyrektywa generuje również `UWOP_SET_FPREG` wpis kodu unwind dla określonego rejestru przy użyciu bieżącego przesunięcia prologu.

## <a name="syntax"></a>Składnia

> **. SETFRAME** *reg*, *offset*

## <a name="remarks"></a>Uwagi

**. Funkcja SETFRAME** umożliwia ml64.exe użytkownikom Określanie sposobu odwinięcia funkcji ramki i jest dozwolona tylko w obrębie prologu, która rozciąga się od deklaracji Frame [proces](proc.md) do [. ENDPROLOG](dot-endprolog.md) . Dyrektywy te nie generują kodu; generują one tylko `.xdata` i `.pdata` . **. Instrukcja SETFRAME** powinna być poprzedzona instrukcjami, które faktycznie implementują akcje, które mają być odwiązane. Dobrym sposobem jest Zawijanie dyrektyw unwind i kodu, które są przeznaczone do odwinięcia w makrze w celu zapewnienia zgody.

Aby uzyskać więcej informacji, zobacz [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Sample

### <a name="description"></a>Opis

Poniższy przykład pokazuje, jak używać wskaźnika ramki:

### <a name="code"></a>Kod

```asm
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE
_text SEGMENT
frmex2 PROC FRAME
   push rbp
.pushreg rbp
   sub rsp, 010h
.allocstack 010h
   mov rbp, rsp
.setframe rbp, 0
.endprolog
   ; modify the stack pointer outside of the prologue (similar to alloca)
   sub rsp, 060h

   ; we can unwind from the following AV because of the frame pointer
   mov rax, 0
   mov rax, [rax] ; AV!

   add rsp, 060h
   add rsp, 010h
   pop rbp
   ret
frmex2 ENDP
_text ENDS
END
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
