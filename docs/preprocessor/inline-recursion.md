---
description: 'Dowiedz się więcej na temat: inline_recursion pragma'
title: inline_recursion, pragma
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 1688eb724a9a76ce3f173c7f9eac7d52032fbe13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236376"
---
# <a name="inline_recursion-pragma"></a>inline_recursion, pragma

Kontroluje wbudowane rozwijanie bezpośrednich lub wzajemnie cyklicznych wywołań funkcji.

## <a name="syntax"></a>Składnia

> **#pragma inline_recursion (** [{ **on**  |  **off** }] **)**

## <a name="remarks"></a>Uwagi

Użyj tej dyrektywy pragma, aby kontrolować funkcje oznaczone jako [inline](../cpp/inline-functions-cpp.md) i [__inline](../cpp/inline-functions-cpp.md) lub funkcje, które kompilator automatycznie rozszerza w obszarze `/Ob2` opcji. Użycie tej dyrektywy pragma wymaga ustawienia opcji kompilatora [/ob](../build/reference/ob-inline-function-expansion.md) o wartości 1 lub 2. Domyślny stan **inline_recursion** jest wyłączony. Ta pragma jest skuteczna przy pierwszym wywołaniu funkcji po pojawieniu się dyrektywy pragma i nie ma wpływu na definicję funkcji.

**Inline_recursion** pragma kontroluje sposób rozszerzania funkcji cyklicznych. Jeśli **inline_recursion** jest wyłączona, a jeśli Wbudowana funkcja wywołuje siebie bezpośrednio lub pośrednio, funkcja zostanie rozwinięta tylko raz. Jeśli **inline_recursion** jest włączona, funkcja jest rozszerzana wiele razy, dopóki nie osiągnie wartości ustawionej za pomocą [inline_depth](../preprocessor/inline-depth.md) pragma, wartość domyślna funkcji cyklicznych, która jest definiowana przez `inline_depth` pragma lub limit pojemności.

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/Ob (rozszerzenie funkcji wbudowanej)](../build/reference/ob-inline-function-expansion.md)
