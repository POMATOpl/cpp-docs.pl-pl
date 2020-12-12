---
description: 'Dowiedz się więcej na temat: _emit pseudoinstruction'
title: Pseudoinstrukcja _emit
ms.date: 08/30/2018
f1_keywords:
- _emit
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
ms.openlocfilehash: d3e2a39312c94ff0e4868bed9afa74011051a129
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117812"
---
# <a name="_emit-pseudoinstruction"></a>Pseudoinstrukcja _emit

**Specyficzne dla firmy Microsoft**

Pseudoinstruction **_emit** definiuje jeden bajt w bieżącej lokalizacji w bieżącym segmencie tekstu. Pseudoinstruction **_emit** jest podobna do dyrektywy [DB](../../assembler/masm/db.md) of MASM.

Poniższy fragment umieszcza bajty 0x4A, 0x43 i 0x4B w kodzie:

```cpp
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B
.
.
.
__asm {
    randasm
    }
```

> [!CAUTION]
> W przypadku `_emit` generowania instrukcji modyfikujących rejestry i kompilowania aplikacji przy użyciu optymalizacji kompilator nie może określić, których rejestrów dotyczy. Na przykład jeśli `_emit` generuje instrukcję modyfikującą rejestr **RAX** , kompilator nie wie, że **RAX** uległy zmianie. Kompilator może następnie wprowadzić nieprawidłowe założenie dotyczące wartości w tym rejestrze po wykonaniu kodu asemblera wbudowanego. W związku z tym aplikacja może wykazywać nieprzewidywalne zachowanie podczas jego uruchamiania.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
