---
description: 'Dowiedz się więcej na temat: EXTERNDEF'
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: b0ffc2154996fc7cea9f0b61917cadf7b776972f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130328"
---
# <a name="externdef"></a>EXTERNDEF

Definiuje co najmniej jedną zmienną zewnętrzną, etykiety lub symbole o nazwie *name* , której typem jest *Typ*.

## <a name="syntax"></a>Składnia

> **EXTERNDEF** ⟦*Language-Type*⟧ __:__*Type* ⟦__,__ ⟦*Language-Type*⟧ *name*__:__*Type* ... ⟧

## <a name="remarks"></a>Uwagi

Argument *typu Language* jest prawidłowy tylko w 32-bitowym MASM.

Jeśli *Nazwa* jest zdefiniowana w module, jest traktowana jako [publiczna](public-masm.md). Jeśli *Nazwa* jest przywoływana w module, jest traktowana jako [extern](extern-masm.md). Jeśli *Nazwa* nie jest przywoływana, zostanie zignorowana. *Typ* może być typem [ABS](operator-abs.md), który importuje *nazwę* jako stałą. Zwykle używane w plikach include.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
