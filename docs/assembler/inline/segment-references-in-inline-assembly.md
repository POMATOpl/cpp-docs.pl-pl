---
description: 'Dowiedz się więcej na temat: odwołania do segmentów w zestawie wbudowanym'
title: Odwołania do segmentu w zestawie wbudowanym
ms.date: 08/30/2018
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
ms.openlocfilehash: 9f9f37d7c45700358cc958f12d6f2d97da6bcf01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122086"
---
# <a name="segment-references-in-inline-assembly"></a>Odwołania do segmentu w zestawie wbudowanym

**Specyficzne dla firmy Microsoft**

Należy odwołać się do segmentów, rejestrując zamiast nazwy (nazwa segmentu `_TEXT` jest nieprawidłowa, na przykład). Zastąpienia segmentu muszą używać rejestru jawnie, jak w ES: [BX].

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
