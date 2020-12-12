---
description: Dowiedz się więcej na temat Assembly-Language komentarzy
title: Komentarze języka zestawu
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: 704f5275afe5cb5629b2e7667fe9107417512198
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118007"
---
# <a name="assembly-language-comments"></a>Komentarze języka zestawu

**Specyficzne dla firmy Microsoft**

Instrukcje w **`__asm`** bloku mogą korzystać z komentarzy do języka zestawu:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Ponieważ makra języka C są rozwijane do pojedynczej linii logicznej, Unikaj korzystania z komentarzy w języku asemblera w makrach. (Zobacz [Definiowanie bloków __asm jako makr C](../../assembler/inline/defining-asm-blocks-as-c-macros.md)). **`__asm`** Blok może również zawierać komentarze w stylu C. Aby uzyskać więcej informacji, zobacz [Używanie języka c lub C++ w blokach __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
