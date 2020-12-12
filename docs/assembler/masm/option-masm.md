---
description: 'Dowiedz się więcej o: opcja'
title: OPTION (MASM)
ms.date: 07/15/2020
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: e2ab1f232b63c2a368204584c1fed69efb40e6ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97126233"
---
# <a name="option"></a>OPTION

Włącza i wyłącza funkcje asemblera.

## <a name="syntax"></a>Składnia

> **`OPTION`***Lista opcji*

## <a name="remarks"></a>Uwagi

Dostępne opcje to:

:::row:::
   :::column span="":::
      **`CASEMAP`**\
      **`DOTNAME`**\
      **`NODOTNAME`**\
      **`EMULATOR`**\
      **`NOEMULATOR`**\
      **`EPILOGUE`**\
      **`EXPR16`**
   :::column-end:::
   :::column span="":::
      **`EXPR32`**\
      **`LANGUAGE`**\
      **`LJMP`**\
      **`NOLJMP`**\
      **`M510`**\
      **`NOM510`**\
      **`NOKEYWORD`**
   :::column-end:::
   :::column span="":::
      **`NOSIGNEXTEND`**\
      **`OFFSET`**\
      **`OLDMACROS`**\
      **`NOOLDMACROS`**\
      **`OLDSTRUCTS`**\
      **`NOOLDSTRUCTS`**\
      **`PROC`**
   :::column-end:::
   :::column span="":::
      **`PROLOGUE`**\
      **`READONLY`**\
      **`NOREADONLY`**\
      **`SCOPED`**\
      **`NOSCOPED`**\
      **`SEGMENT`**\
      **`SETIF2`**
   :::column-end:::
:::row-end:::

Składnia języka to **`OPTION LANGUAGE:`** _`x`_ , gdzie *`x`* jest jedną z,, **`C`** **`SYSCALL`** ,, **`STDCALL`** **`PASCAL`** **`FORTRAN`** , lub **`BASIC`** . **`SYSCALL`**, **`PASCAL`** , **`FORTRAN`** i **`BASIC`** nie są obsługiwane w programie [`.MODEL`](dot-model.md) **`FLAT`** .

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
