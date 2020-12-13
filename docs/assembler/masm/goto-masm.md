---
description: 'Dowiedz się więcej na temat: GOTO'
title: GOTO (MASM)
ms.date: 12/16/2019
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: ab373d77cbfb660d4cc256e39de38b7f066eac27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130263"
---
# <a name="goto"></a>GOTO

Przenosi zestaw do wiersza oznaczonego **:**_macrolabel_.

## <a name="syntax"></a>Składnia

> **Przejdź** do *macrolabel*

## <a name="remarks"></a>Uwagi

**Polecenie goto** jest dozwolone tylko wewnątrz [makra](macro.md), [dla](for-masm.md), [FORC](forc.md), [REPEAT](repeat.md)i [while](while-masm.md) . Wartość docelowa *macrolabel* musi być jedyną dyrektywą w wierszu i musi być poprzedzona znakiem dwukropka.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
