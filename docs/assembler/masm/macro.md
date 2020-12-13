---
description: 'Dowiedz się więcej na temat: MACRO'
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 5410357e76d28cddd54f3c90a34d3e85b8629143
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129743"
---
# <a name="macro"></a>MACRO

Oznacza blok makra o nazwie *name* i ustanawia symbole zastępcze *parametru* dla argumentów przewidzianych podczas wywoływania makra.

## <a name="syntax"></a>Składnia

> *Nazwij***makro** ⟦*parametr* ⟦**: REQ** | : =*default*  |  *args* **: vararg**⟧... ⟧\  
> *zatwierdzeni*\
⟦**Goto** :*macrolabelId*⟧ \
> ⟦**EXITM**⟧ \
> **ENDM** ⟦*wartość*⟧

## <a name="remarks"></a>Uwagi

Funkcja makro zwraca *wartość* do instrukcji wywołującej.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[GOTO (MASM)](goto-masm.md)\
[ENDM](endm.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
