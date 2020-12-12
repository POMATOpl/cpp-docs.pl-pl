---
description: 'Dowiedz się więcej na temat: ALIGN'
title: ALIGN (MASM)
ms.date: 12/17/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: d13fce5d70d96e4e88a3f1044f633be0145a3fc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121774"
---
# <a name="align"></a>ALIGN

Dyrektywa **align** wyrównuje następny element danych lub instrukcję na adres, który jest wielokrotnością jego parametru. Parametr musi być potęgą liczby 2 (na przykład 1, 2, 4 itd.), która jest mniejsza lub równa wyrównaniu segmentu.

## <a name="syntax"></a>Składnia

> **Wyrównaj** ⟦*constantExpression*⟧

## <a name="remarks"></a>Uwagi

Dyrektywa **align** pozwala określić początkowe przesunięcie elementu danych lub instrukcji. Wyrównane dane mogą zwiększyć wydajność, kosztem bezstratnego miejsca między elementami danych. Ulepszenia dużej wydajności mogą być widoczne, gdy dostęp do danych znajduje się w granicach, które pasują do wierszy pamięci podręcznej. Dostęp do naturalnych granic dla typów natywnych oznacza krótszy czas poświęcany na wewnętrzną redopasowanie sprzętu włączenia mikrokodu.

Potrzeba wyrównanych instrukcji jest rzadki w nowoczesnych procesorach, które używają prostego modelu adresowania, ale mogą być wymagane w celu przechodzenia w starszym kodzie dla innych modeli adresowania.

Gdy dane są wyrównane, pominięte miejsce jest uzupełnione zerami. Gdy instrukcje są wyrównane, pominięte miejsce jest wypełniane odpowiednio NOP instrukcjami.

## <a name="see-also"></a>Zobacz też

[CHOĆBY](even.md)\
[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
