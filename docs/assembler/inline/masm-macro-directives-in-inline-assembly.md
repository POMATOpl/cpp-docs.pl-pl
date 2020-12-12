---
description: 'Dowiedz się więcej na temat: dyrektywy makra MASM w zestawie wbudowanym'
title: Dyrektywy makra MASM w zestawie wbudowanym
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 131066ad117e0f314ba0900e8ecd19eb4843c25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117565"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Dyrektywy makra MASM w zestawie wbudowanym

**Specyficzne dla firmy Microsoft**

Asembler wbudowany nie jest asemblerem makra. Nie można użyć dyrektyw makra MASM (**makra**, `REPT` , **IRC**, `IRP` i `ENDM` ) lub operatorów makr ( **<>** , **!**, **&** , `%` i `.TYPE` ). **`__asm`** Blok może jednak korzystać z dyrektyw preprocesora języka C. Aby uzyskać więcej informacji [, zobacz Używanie języka C lub C++ w blokach __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
