---
description: 'Dowiedz się więcej na temat: Używanie symboli C lub C++ w blokach __asm'
title: Użycie symboli C lub C++ w blokach __asm
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
ms.openlocfilehash: 3a2e46ab13bb316cb4761103d34da6c129c97995
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121891"
---
# <a name="using-c-or-c-symbols-in-__asm-blocks"></a>Użycie symboli C lub C++ w blokach __asm

**Specyficzne dla firmy Microsoft**

**`__asm`** Blok może odwoływać się do dowolnego symbolu C lub C++ w zakresie, w którym znajduje się blok. (Symbole C i C++ są nazwami zmiennych, nazwami funkcji i etykietami, czyli nazwami, które nie są symbolicznymi ani **`enum`** elementami członkowskimi). Nie można wywołać funkcji składowych języka C++.)

Istnieją pewne ograniczenia dotyczące używania symboli C i C++:

- Każda instrukcja języka asemblera może zawierać tylko jeden symbol C lub C++. Wiele symboli może występować w tej samej instrukcji zestawu tylko z wyrażeniami **długości**, **typu** i **rozmiaru** .

- Funkcje, do których odwołuje się **`__asm`** blok, muszą być zadeklarowane we wcześniejszej części tego programu. W przeciwnym razie kompilator nie może rozróżnić nazw funkcji i etykiet w **`__asm`** bloku.

- **`__asm`** Blok nie może używać żadnych symboli C lub C++ o takich samych pisowniach jak słowa zastrzeżone MASM (niezależnie od wielkości liter). Słowa zastrzeżone MASM zawierają nazwy instrukcji, takie jak **push** i Register Names, takie jak si.

- Tagi struktury i Unii nie są rozpoznawane w **`__asm`** blokach.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Używanie C lub C++ w blokach __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
