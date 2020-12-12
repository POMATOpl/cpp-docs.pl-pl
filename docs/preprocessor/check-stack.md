---
description: 'Dowiedz się więcej na temat: check_stack pragma'
title: check_stack, pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 55a639e22ded788bd731aad83eb7918e1006ae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300856"
---
# <a name="check_stack-pragma"></a>check_stack, pragma

Instruuje kompilator, aby wyłączył sondy stosu, jeśli określono wartość **off** (lub **-** ) lub aby włączyć sondy stosu, jeśli określono wartość **on** (lub **+** ).

## <a name="syntax"></a>Składnia

> **#pragma check_stack (** [{ **on**  |  **off** }] **)**\
> **#pragma check_stack** { **+**  |  **-** }

## <a name="remarks"></a>Uwagi

Ta pragma jest skuteczna przy pierwszej funkcji zdefiniowanej po wystąpieniu dyrektywy pragma. Sondy stosu nie są częścią makr ani funkcji, które są generowane w tekście.

Jeśli nie podajesz argumentu dla **check_stack** pragma, sprawdzanie stosu zostanie przywrócone do zachowania określonego w wierszu polecenia. Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](../build/reference/compiler-options.md). `#pragma check_stack`W poniższej tabeli zestawiono interakcję i opcję [/GS](../build/reference/gs-control-stack-checking-calls.md) .

### <a name="using-the-check_stack-pragma"></a>Używanie dyrektywy pragma check_stack

|Składnia|Skompilowane z<br /><br /> Opcja/GS?|Akcja|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` lub<br /><br /> `#pragma check_stack`|Tak|Wyłącza sprawdzanie stosu dla następujących funkcji|
|`#pragma check_stack( )` lub<br /><br /> `#pragma check_stack`|Nie|Włącza sprawdzanie stosu dla następujących funkcji|
|`#pragma check_stack(on)`<br /><br /> oraz `#pragma check_stack +`|Tak lub Nie|Włącza sprawdzanie stosu dla następujących funkcji|
|`#pragma check_stack(off)`<br /><br /> oraz `#pragma check_stack -`|Tak lub Nie|Wyłącza sprawdzanie stosu dla następujących funkcji|

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
