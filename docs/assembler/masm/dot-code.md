---
description: Dowiedz się więcej na temat:. KODU
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 3f47b3bf9f345ae39f68b1b21e8f3807f554ea2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132279"
---
# <a name="code"></a>.CODE

(tylko 32-bitowy MASM). W przypadku użycia z [. MODEL](dot-model.md)wskazuje początek segmentu kodu.

## <a name="syntax"></a>Składnia

> **. KOD** ⟦*Nazwa*⟧ \
> ⟦ *segmentItem* ⟧... \
> ⟦ *codesegmentnameId* **;;** ⟧\

### <a name="parameters"></a>Parametry

*Nazwij*\
Opcjonalny parametr, który określa nazwę segmentu kodu. Domyślna nazwa jest **_TEXT** dla [modeli](dot-model.md)bardzo mały, mały, kompaktowy i płaski. Nazwa domyślna to *modulename* _TEXT dla innych modeli.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[. DATA](dot-data.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
