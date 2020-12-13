---
description: Dowiedz się więcej na temat:. SAVEREG
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 8b946c9b25c3f4dc6a4696b418e85487e20014eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131186"
---
# <a name="savereg"></a>.SAVEREG

Generuje `UWOP_SAVE_NONVOL` `UWOP_SAVE_NONVOL_FAR` wpis kodu lub unwind dla określonego rejestru (*reg*) i przesunięcia (*przesunięcie*) przy użyciu bieżącego przesunięcia prologu. MASM będzie wybierać najbardziej wydajne kodowanie.

## <a name="syntax"></a>Składnia

> **. SAVEREG** *reg*__,__ *przesunięcie*

## <a name="remarks"></a>Uwagi

**. SAVEREG** ml64.exe umożliwia użytkownikom Określanie sposobu odwinięcia funkcji ramki i jest dozwolony tylko w obrębie prologu, który rozciąga się od deklaracji Frame [proces](proc.md) do [. ENDPROLOG](dot-endprolog.md) . Dyrektywy te nie generują kodu; generują one tylko `.xdata` i `.pdata` . **. SAVEREG** powinien być poprzedzony instrukcjami, które faktycznie implementują akcje, które mają być odwiązane. Dobrym sposobem jest Zawijanie dyrektyw unwind i kodu, które są przeznaczone do odwinięcia w makrze w celu zapewnienia zgody.

Aby uzyskać więcej informacji, zobacz [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
