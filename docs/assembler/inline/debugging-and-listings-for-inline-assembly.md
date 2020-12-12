---
description: 'Dowiedz się więcej o: debugowanie i listy dla zestawu wbudowanego'
title: Debugowanie i listy dla zestawu wbudowanego
ms.date: 08/30/2018
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
ms.openlocfilehash: b4608a0176de5e061d7dc7f15b8758d9bd3a94b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117873"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Debugowanie i listy dla zestawu wbudowanego

**Specyficzne dla firmy Microsoft**

Programy zawierające kod asemblera wbudowanego mogą być debugowane przy użyciu debugera na poziomie źródła, Jeśli kompilujesz za pomocą opcji [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) .

W debugerze można ustawić punkty przerwania zarówno dla języka C, jak i C++ oraz wierszy asemblera. W przypadku włączenia zestawu mieszanego i trybu źródłowego można wyświetlić zarówno źródłowy, jak i rozmontowany formularz kodu zestawu.

Należy zauważyć, że umieszczenie wielu instrukcji zestawu lub instrukcji języka źródłowego w jednym wierszu może obsłużyć debugowanie. W trybie źródłowym można użyć debugera, aby ustawić punkty przerwania w pojedynczym wierszu, ale nie w poszczególnych instrukcjach w tym samym wierszu. Ta sama zasada ma zastosowanie do **`__asm`** bloku zdefiniowanego jako makro języka C, które rozwija się do pojedynczej linii logicznej.

Jeśli utworzysz Źródło mieszane i listę zestawu przy użyciu opcji kompilatora [/FAS](../../build/reference/fa-fa-listing-file.md) , lista zawiera zarówno formularze źródłowe, jak i zestawy poszczególnych wierszy w języku. Makra nie są rozwinięte na listach, ale są rozwinięte podczas kompilacji.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Korzystanie z języka zestawu w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
