---
description: 'Dowiedz się więcej na temat: MMWORD'
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: f0e888efcfea7c1ca94129ff3e4cd2f40644ae13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128236"
---
# <a name="mmword"></a>MMWORD

Używany do 64-bitowego operandów multimediów z instrukcjami MMX i SSE (XMM).

## <a name="syntax"></a>Składnia

> **MMWORD**

## <a name="remarks"></a>Uwagi

**MMWORD** jest typem.  Przed dodaniem **MMWORD** do MASM można osiągnąć równoważne funkcje przy użyciu:

```asm
    mov mm0, qword ptr [ebx]
```

Chociaż obie instrukcje działają na 64-bitowych operandach, **Qword** jest typem dla 64-bitowych liczb całkowitych bez znaku, a **MMWORD** jest typem dla 64-bitowej wartości multimedialnej.

**MMWORD** jest przeznaczony do reprezentowania tego samego typu co [__m64](../../cpp/m64.md).

## <a name="example"></a>Przykład

```asm
    movq     mm0, mmword ptr [ebx]
```

## <a name="see-also"></a>Zobacz też

[MASM BNF, gramatyka](masm-bnf-grammar.md)
