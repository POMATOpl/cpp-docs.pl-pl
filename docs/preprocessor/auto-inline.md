---
description: 'Dowiedz się więcej na temat: auto_inline pragma'
title: auto_inline, pragma
ms.date: 08/29/2019
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: f629bbe5dc47ba15bba5b2b55541509f421fcd8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301051"
---
# <a name="auto_inline-pragma"></a>auto_inline, pragma

Wyklucza wszelkie funkcje zdefiniowane w zakresie, w którym wartość **off** jest określana jako kandydatów do automatycznego rozwijania wbudowanego.

## <a name="syntax"></a>Składnia

> **#pragma auto_inline (** [{ **on**  |  **off** }] **)**

## <a name="remarks"></a>Uwagi

Aby użyć dyrektywy pragma **auto_inline** , umieść ją przed i natychmiast po, a nie wewnątrz, definicję funkcji. Pragma jest skuteczna, gdy tylko pierwsza definicja funkcji zostanie wyświetlona.

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
