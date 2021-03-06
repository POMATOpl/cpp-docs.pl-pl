---
description: 'Dowiedz się więcej na temat: asembler wbudowany'
title: Asembler wbudowany
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
ms.openlocfilehash: 67ae8c40dee71f693dd6641dd81e8f61b8536a1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117773"
---
# <a name="inline-assembler"></a>Asembler wbudowany

**Specyficzne dla firmy Microsoft**

Język asembler ma wiele zastosowań, takich jak poprawa szybkości działania programu, zmniejszenie wymagań dotyczących pamięci i kontrola sprzętu. Można użyć wbudowanego asemblera, aby osadzić instrukcje języka asemblera bezpośrednio w programach źródłowych C i C++, bez dodatkowych kroków asemblacji i łączenia. Asembler wbudowany jest wbudowany w kompilator, więc nie ma potrzeby stosowania oddzielnego asemblera, jak Microsoft Macro Assembler (MASM).

> [!NOTE]
> Programy z kodem wbudowanego asemblera nie są całkowicie przenośne na inne platformy sprzętowe. Jeśli projektujesz do celów przenośności, unikaj stosowania asemblera wbudowanego.

Wbudowany zestaw nie jest obsługiwany w procesorach ARM i x64.  W następujących tematach opisano, jak używać asemblera wbudowanego Visual C/C++ z procesorami x86:

- [Przegląd wbudowanego asemblera](../../assembler/inline/inline-assembler-overview.md)

- [Zalety zestawu wbudowanego](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [Używanie C lub C++ w blokach __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [Używanie i zachowywanie rejestrów w zestawie wbudowanym](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [Przeskocz do etykiet w zestawie wbudowanym](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [Wywoływanie funkcji C w zestawie wbudowanym](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [Wywoływanie funkcji C++ w zestawie wbudowanym](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [Definiowanie bloków __asm jako makr C](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [Optymalizacja wbudowanego zestawu](../../assembler/inline/optimizing-inline-assembly.md)

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora i język asemblera](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[Dokumentacja języka C++](../../cpp/cpp-language-reference.md)<br/>
