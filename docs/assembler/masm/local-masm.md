---
description: 'Dowiedz się więcej na temat: LOCAL'
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 27296f69b62de0dcd314b2575f045e06576bbf64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129756"
---
# <a name="local"></a>LOCAL

W pierwszej dyrektywie w makrze **lokalna** definiuje etykiety, które są unikatowe dla każdego wystąpienia makra.

## <a name="syntax"></a>Składnia

> **Local** *LocalId* ⟦, *LocalId* ... ⟧
>
> **Local** *labelId* ⟦ __\[__ *Count*__]__ ⟧ ⟦__:__*kwalifikowanatype*⟧ ⟦__,__ *labelId* ⟦ __\[__ *Count*__]__ ⟧ ⟦*kwalifikowanatype*⟧... ⟧

## <a name="remarks"></a>Uwagi

W drugiej dyrektywie, w ramach definicji procedury (**proc**), **lokalna** tworzy zmienne oparte na stosie, które istnieją na czas trwania tej procedury. *LabelId* może być prostą zmienną lub tablicą zawierającą elementy *Count* , gdzie *Count* jest wyrażeniem stałym.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
