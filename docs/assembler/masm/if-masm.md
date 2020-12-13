---
description: 'Dowiedz się więcej o programie: Jeśli'
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 09b4bd09155ef848ad165b4e8b0d3a093ade0008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130212"
---
# <a name="if"></a>IF

Przyznaje zestaw elementu *ifstatements* , jeśli *wyrażenie1* ma wartość true (niezerowa) lub *elseifstatements* , jeśli *wyrażenie1* ma wartość false (0), a *wyrażenie2* ma wartość true.

## <a name="syntax"></a>Składnia

> **If** *wyrażenie1*\
> *If-— instrukcje*\
> ⟦**ElseIf** *wyrażenie2*\
> *ElseIf-Statements*⟧ \
> ⟦\
> *else-instrukcje*⟧ \
> **ENDIF**

## <a name="remarks"></a>Uwagi

Następujące dyrektywy mogą zostać zastąpione przez [ElseIf](elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI**, **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB** i **ELSEIFNDEF**. Opcjonalnie należy połączyć *inne instrukcje* , jeśli poprzednie wyrażenie ma wartość false. Należy zauważyć, że wyrażenia są oceniane w czasie montażu.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
