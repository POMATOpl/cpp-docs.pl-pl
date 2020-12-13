---
description: Dowiedz się więcej na temat:. IF (32-bitowy MASM)
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e6ce9695f90a90665aee1cdaf15167963360fe04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131680"
---
# <a name="if-32-bit-masm"></a>. IF (32-bitowy MASM)

Generuje kod, który testuje *condition1* (na przykład AX > 7) i wykonuje *instrukcje* , jeśli warunek ma wartość true. (tylko 32-bitowy MASM).

## <a name="syntax"></a>Składnia

> **. Jeśli** *condition1*\
> *zatwierdzeni*\
> ⟦**.** *Condition2* ElseIf\
> *instrukcje*⟧ \
> ⟦**. ELSE**\
> *instrukcje*⟧ \
> **. ENDIF**

## <a name="remarks"></a>Uwagi

Jeśli [. W przeciwnym](dot-else.md) razie instrukcje są wykonywane, jeśli oryginalny warunek miał wartość false. Należy zauważyć, że warunki są oceniane w czasie wykonywania.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
