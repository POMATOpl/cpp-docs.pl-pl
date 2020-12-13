---
description: 'Dowiedz się więcej na temat: EXTERN'
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 354a390a16fb663dc6e907e37022a362c3ab5648
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130354"
---
# <a name="extern"></a>EXTERN

Definiuje co najmniej jedną zmienną zewnętrzną, etykiety lub symbole o nazwie *name* , której typem jest *Typ*.

## <a name="syntax"></a>Składnia

> **Extern** ⟦*Language-Type*⟧ *name* ⟦ __(__*Altid*__)__ ⟧ __:__ *Type* ⟦__,__ ⟦*Language-Type*⟧ *name* ⟦ __(__*Altid*__)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Uwagi

Argument *typu Language* jest prawidłowy tylko w 32-bitowym MASM.

*Typ* może być typem [ABS](operator-abs.md), który importuje *nazwę* jako stałą. Analogicznie jak [EXTRN](extrn.md).

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
