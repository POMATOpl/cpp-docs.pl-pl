---
description: Dowiedz się więcej o tym, jak napisać filtr wyjątku strukturalnego.
title: Pisanie filtru wyjątku
ms.date: 12/16/2020
helpviewer_keywords:
- exception handling [C++], filters
ms.openlocfilehash: 8b6706c7dfe0e96e26f77f1f3a452db638141803
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645062"
---
# <a name="writing-an-exception-filter"></a>Pisanie filtru wyjątku

Możesz obsłużyć wyjątek wykonując skok na poziom programu obsługi wyjątków lub kontynuując wykonywanie. Zamiast używać kodu programu obsługi wyjątków do obsługi wyjątku i przechodzenia przez program, można użyć wyrażenia *filtru* , aby usunąć problem. Następnie przez zwrócenie `EXCEPTION_CONTINUE_EXECUTION` (-1) można wznowić normalny przepływ bez wyczyszczenia stosu.

> [!NOTE]
> Niektóre wyjątki nie mogą być kontynuowane. Jeśli *Filtr* zwróci wartość-1 dla takiego wyjątku, system zgłasza nowy wyjątek. Po wywołaniu należy [`RaiseException`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) określić, czy wyjątek będzie kontynuowany.

Na przykład poniższy kod używa wywołania funkcji w wyrażeniu *filtru* : Ta funkcja obsługuje problem, a następnie zwraca-1, aby wznowić normalny przepływ sterowania:

```cpp
// exceptions_Writing_an_Exception_Filter.cpp
#include <windows.h>
int main() {
   int Eval_Exception( int );

   __try {}

   __except ( Eval_Exception( GetExceptionCode( ))) {
      ;
   }

}
void ResetVars( int ) {}
int Eval_Exception ( int n_except ) {
   if ( n_except != STATUS_INTEGER_OVERFLOW &&
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions
   return EXCEPTION_CONTINUE_SEARCH;

   // Execute some code to clean up problem
   ResetVars( 0 );   // initializes data to 0
   return EXCEPTION_CONTINUE_EXECUTION;
}
```

Dobrym pomysłem jest użycie wywołania funkcji w wyrażeniu *filtru* za każdym razem, gdy *Filtr* musi wykonać dowolne złożone elementy. Obliczanie wyrażenia powoduje wykonanie funkcji, w tym przypadku jest to `Eval_Exception`.

Zwróć uwagę na użycie, [`GetExceptionCode`](/windows/win32/Debug/getexceptioncode) Aby określić wyjątek. Ta funkcja musi być wywołana wewnątrz wyrażenia filtru **`__except`** instrukcji. `Eval_Exception` nie można wywołać `GetExceptionCode` , ale musi mieć do niego przesłany kod wyjątku.

Ten program obsługi wyjątków przekazuje sterowanie do innego programu obsługi wyjątków, o ile wyjątek nie dotyczy przepełnienia liczby całkowitej lub zmiennoprzecinkowej. Jeśli tak się stanie, program obsługi wyjątku wywołuje funkcję (`ResetVars` jest tylko przykładem, a nie funkcją API), aby zresetować niektóre zmienne globalne. **`__except`** Blok instrukcji, który w tym przykładzie jest pusty, nigdy nie może zostać wykonany, ponieważ `Eval_Exception` nigdy nie zwraca `EXCEPTION_EXECUTE_HANDLER` (1).

Używanie wywołań funkcji jest dobrą techniką ogólnego przeznaczenia do radzenia sobie ze złożonymi wyrażeniami filtrującymi. Dwie inne funkcje języka C, które są przydatne to:

- Operator warunkowy

- Operator przecinka

Operator warunkowy jest często przydatny w tym miejscu. Można go użyć do sprawdzenia określonego kodu powrotu, a następnie zwrócenia jednej z dwóch różnych wartości. Na przykład filtr w poniższym kodzie rozpoznaje wyjątek tylko wtedy, gdy wyjątek jest `STATUS_INTEGER_OVERFLOW` :

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

Celem operatora warunkowego w tym przypadku jest głównie zapewnienie czytelności, ponieważ następujący kod generuje te same wyniki:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

Operator warunkowy jest bardziej użyteczny w sytuacjach, w których filtr ma być obliczany na wartość-1 `EXCEPTION_CONTINUE_EXECUTION` .

Operator przecinek umożliwia wykonywanie wielu wyrażeń w sekwencji. Następnie zwraca wartość ostatniego wyrażenia. Na przykład, poniższy kod przechowuje kod wyjątku w zmiennej, a następnie ją sprawdza:

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>Zobacz także

[Pisanie programu do obsługi wyjątku](../cpp/writing-an-exception-handler.md)<br/>
[Obsługa wyjątków strukturalnych (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
