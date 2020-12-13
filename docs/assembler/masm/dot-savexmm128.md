---
description: Dowiedz się więcej na temat:. SAVEXMM128
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 697598aa5820b029d19da62a817c60455059865e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131121"
---
# <a name="savexmm128"></a>.SAVEXMM128

Generuje `UWOP_SAVE_XMM128` `UWOP_SAVE_XMM128_FAR` wpis kodu lub unwind dla określonego rejestru XMM i przesunięcia przy użyciu bieżącego przesunięcia prologu. MASM będzie wybierać najbardziej wydajne kodowanie.

## <a name="syntax"></a>Składnia

> **. SAVEXMM128** *xmmreg* , *offset*

## <a name="remarks"></a>Uwagi

**. SAVEXMM128** ml64.exe umożliwia użytkownikom Określanie, jak działa funkcja ramki, i jest dozwolona tylko w prologu, która rozciąga się od deklaracji Frame [proces](proc.md) do [. ENDPROLOG](dot-endprolog.md) . Dyrektywy te nie generują kodu; generują one tylko `.xdata` i `.pdata` . . SAVEXMM128 powinien być poprzedzony instrukcjami, które faktycznie implementują akcje, które mają być odwiązane. Dobrym sposobem jest Zawijanie dyrektyw unwind i kodu, które są przeznaczone do odwinięcia w makrze w celu zapewnienia zgody.

*przesunięcie* musi być wielokrotnością 16.

Aby uzyskać więcej informacji, zobacz [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
