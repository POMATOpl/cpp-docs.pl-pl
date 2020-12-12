---
description: 'Dowiedz się więcej na temat: wywoływanie funkcji C++ w zestawie wbudowanym'
title: Wywoływanie funkcji C++ w asemblerze wbudowanym
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 3efd4f00eae5810b287a27546bba3160f479b8f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117968"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Wywoływanie funkcji C++ w asemblerze wbudowanym

**Specyficzne dla firmy Microsoft**

**`__asm`** Blok może wywoływać tylko globalne funkcje C++, które nie są przeciążone. Jeśli wywołasz przeciążoną globalną funkcję C++ lub funkcję członkowską języka C++, kompilator wygeneruje błąd.

Możesz również wywołać wszystkie funkcje zadeklarowane za pomocą zewnętrznego powiązania **"C"** . Dzięki temu **`__asm`** blok w ramach programu C++ może wywoływać funkcje biblioteki języka C, ponieważ wszystkie standardowe pliki nagłówkowe deklarują funkcje biblioteki jako zewnętrzne powiązania **"C"** .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Asembler wbudowany](../../assembler/inline/inline-assembler.md)<br/>
