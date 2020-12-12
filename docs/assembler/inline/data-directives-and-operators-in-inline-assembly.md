---
description: 'Dowiedz się więcej o: dyrektywy danych i operatory w zestawie wbudowanym'
title: Dyrektywy danych i operatory w zestawie wbudowanym
ms.date: 08/30/2018
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
ms.openlocfilehash: a2b11aa95723245fc977f97f42b1de2f6c7306ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117955"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Dyrektywy danych i operatory w zestawie wbudowanym

**Specyficzne dla firmy Microsoft**

Chociaż **`__asm`** blok może odwoływać się do typów danych C lub C++ i obiektów, nie może definiować obiektów danych za pomocą dyrektyw MASM lub operatorów. W szczególnych przypadkach nie można użyć definicji dyrektywy **DB**, `DW` , **DD**, `DQ` , `DT` , i `DF` ani operatora `DUP` lub.  Struktury i rekordy MASM są również niedostępne. Wbudowany asembler nie akceptuje dyrektyw `STRUC` , `RECORD` , **Width** ani **Mask**.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
