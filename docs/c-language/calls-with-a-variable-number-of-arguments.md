---
description: 'Dowiedz się więcej na temat: wywołania z zmienną liczbą argumentów'
title: Wywołania z różną liczbą argumentów
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- arguments [C++], variable number of
- VARARGS.H
- ellipsis (...), variable number of arguments
- STDARGS.H
- function calls, arguments
- '... ellipsis'
- function calls, variable number of arguments
ms.assetid: 8808fb26-4822-42f5-aba3-ac64b54e151b
ms.openlocfilehash: 4e30759d25d7dd3b5b3bcb69c0edc0e97849c7e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214145"
---
# <a name="calls-with-a-variable-number-of-arguments"></a>Wywołania z różną liczbą argumentów

Lista parametrów częściowych może zostać zakończona przez notację wielokropka, przecinek, po którym następuje trzy kropki (**,...**), aby wskazać, że może istnieć więcej argumentów przekazanych do funkcji, ale nie podano więcej informacji o nich. Kontrola typów nie jest wykonywana na takich argumentach. Co najmniej jeden parametr musi poprzedzać notację wielokropka, a notacja wielokropka musi stanowić ostatni token na liście parametrów. Bez notacji wielokropka zachowanie funkcji jest niezdefiniowane, jeżeli otrzyma parametry oprócz tych zadeklarowanych na liście parametrów.

Aby wywołać funkcję o zmiennej liczbie argumentów, wystarczy określić dowolną liczbę argumentów w wywołaniu funkcji. Przykładem jest funkcja `printf` z biblioteki wykonawczej C. Wywołanie funkcji musi zawierać jeden argument dla każdej nazwy typu zadeklarowanej w liście parametrów lub liście typów argumentów.

Wszystkie argumenty określone w wywołaniu funkcji są umieszczane na stosie, o ile nie **`__fastcall`** określono konwencji wywoływania. Liczba parametrów zadeklarowanych dla funkcji określa, ile argumentów pochodzi ze stosu i jest przypisanych do parametrów. Użytkownik jest odpowiedzialny za pobieranie dodatkowych argumentów ze stosu i określanie, ile argumentów jest obecne. Plik STDARG.H zawiera makra stylu ANSI do uzyskiwania dostępu do argumentów funkcji, które mają zmienną liczbę argumentów. Ponadto, makra stylu XENIX w VARARGS.H są nadal obsługiwane.

Ta przykładowa deklaracja dotyczy funkcji, która wywołuje zmienną liczbę argumentów:

```
int average( int first, ...);
```

## <a name="see-also"></a>Zobacz też

[Wywołania funkcji](../c-language/function-calls.md)
