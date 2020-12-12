---
description: 'Dowiedz się więcej na temat: obiekty tymczasowe'
title: Obiekty tymczasowe
ms.date: 11/04/2016
helpviewer_keywords:
- temporary objects
- objects [C++], temporary
ms.assetid: 4c8cec02-391e-4225-9bc6-06d150201412
ms.openlocfilehash: d827568013b3684c2126887d390ecbf223c46da5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164747"
---
# <a name="temporary-objects"></a>Obiekty tymczasowe

W niektórych przypadkach, konieczne jest utworzenie obiektów tymczasowych przez kompilator. Takie obiekty tymczasowe mogą być utworzone z następujących powodów:

- Aby zainicjować **`const`** odwołanie z inicjatorem typu innego niż typ podstawowy inicjowanego odwołania.

- Aby przechowywać wartość zwracaną przez funkcję, która zwraca typ zdefiniowany przez użytkownika. Takie obiekty tymczasowe są tworzone tylko wtedy, gdy program nie kopiuje wartości zwracanej do obiektu. Na przykład:

    ```cpp
    UDT Func1();    //  Declare a function that returns a user-defined
                    //   type.

    ...

    Func1();        //  Call Func1, but discard return value.
                    //  A temporary object is created to store the return
                    //   value.
    ```

   Ponieważ wartość zwracana nie jest kopiowana do innego obiektu, tworzony jest obiekt tymczasowy. Częstszy przypadek tworzenia obiektów tymczasowych występuje w trakcie obliczania wyrażenia, w którym muszą zostać wywołane funkcje przeciążonego operatora. Takie funkcje przeciążonego operatora zwracają typ zdefiniowany przez użytkownika, który często nie jest kopiowany do innego obiektu.

   Rozważ wyrażenie `ComplexResult = Complex1 + Complex2 + Complex3`. Obliczane jest wyrażenie `Complex1 + Complex2`, a wynik jest przechowywany w obiekcie tymczasowym. Następnie obliczane jest *tymczasowe* wyrażenie `+ Complex3` , a wynik jest kopiowany do `ComplexResult` (przy założeniu, że operator przypisania nie jest przeciążony).

- Aby przechować wynik rzutowania na typ zdefiniowany przez użytkownika. Gdy obiekt danego typu jest jawnie konwertowany na typ zdefiniowany przez użytkownika, nowy obiekt jest konstruowany jako obiekt tymczasowy.

Obiekty tymczasowe mają okres istnienia zdefiniowany w punkcie utworzenia oraz punkt, w którym są niszczone. Dowolne wyrażenie, które tworzy co najmniej jeden obiekt tymczasowy, ostatecznie niszczy takie obiekty w kolejności odwrotnej do utworzenia. Punkty, w których występuje niszczenie obiektów pokazano w następującej tabeli.

### <a name="destruction-points-for-temporary-objects"></a>Punkty niszczenia obiektów tymczasowych

|Powód utworzenia obiektów tymczasowych|Punkt niszczenia|
|------------------------------|-----------------------|
|Wynik obliczania wyrażenia|Wszystkie obiekty tymczasowe utworzone w wyniku obliczania wyrażenia są niszczone na końcu instrukcji wyrażenia (czyli w średniku) lub na końcu wyrażeń kontrolnych dla **`for`** , **`if`** ,, **`while`** **`do`** i **`switch`** instrukcji.|
|Inicjowanie **`const`** odwołań|Jeśli inicjator nie jest l-wartością tego samego typu co inicjowane odwołanie, tworzony jest obiekt tymczasowy o typie podstawowym obiektu i inicjowany za pomocą wyrażenia inicjowania. Obiekt tymczasowy jest niszczony natychmiast po zniszczeniu odwoływanego obiektu z którym jest powiązany.|
