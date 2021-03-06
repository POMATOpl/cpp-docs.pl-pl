---
description: 'Dowiedz się więcej na temat: wyrażenia przyrostkowe'
title: Wyrażenia przyrostków
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
ms.openlocfilehash: c6c38fee6b2b44ab9ff390eed8d178bf40653df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258528"
---
# <a name="postfix-expressions"></a>Wyrażenia przyrostków

Wyrażenia przyrostkowe składają się z podstawowego wyrażenia lub wyrażeń, w których operatory przyrostkowe następują po wyrażeniu podstawowym. Operatory przyrostkowe są wymienione w poniższej tabeli.

### <a name="postfix-operators"></a>Operatory przyrostka

|Nazwa operatora|Notacja operatora|
|-------------------|-----------------------|
|[Operator indeksu dolnego](../cpp/subscript-operator.md)|**[ ]**|
|[Operator wywołania funkcji](../cpp/function-call-operator-parens.md)|**( )**|
|[Operator jawnej konwersji typu](../cpp/explicit-type-conversion-operator-parens.md)|*type-name* **()**|
|[Operator dostępu do elementów członkowskich](../cpp/member-access-operators-dot-and.md)|**.** oraz **->**|
|[Operator inkrementacji przyrostkowej](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**++**|
|[Operator dekrementacji przyrostkowej](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|

Następująca składnia opisuje możliwe wyrażenia przyrostkowe:

```
primary-expression
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )
```

*Wyrażenie przyrostkowe* powyżej może być [wyrażeniem podstawowym](primary-expressions.md) lub innym wyrażeniem przyrostkowym. Grupa wyrażeń przyrostkowych od lewej do prawej, umożliwia w ten sposób łączenie wyrażeń w następujący sposób:

```cpp
func(1)->GetValue()++
```

W powyższym wyrażeniu, jest `func` wyrażeniem podstawowym, jest wyrażeniem `func(1)` przyrostkowym funkcji, `func(1)->GetValue` jest wyrażeniem przyrostkowym określającym element członkowski klasy, `func(1)->GetValue()` jest innym wyrażeniem przyrostkowym funkcji, a całe wyrażenie jest wyrażeniem przyrostkowym zwiększającym wartość zwracaną GetValue.  Znaczenie wyrażenia jako całości to „wywołaj funkcję przekazywania 1 jako argument i uzyskaj wskaźnik do klasy jako wartość zwracaną.  Następnie Wywołaj `GetValue()` dla tej klasy, a następnie zwiększ wartość zwracaną.

Wyrażenia wymienione powyżej są wyrażeniami przypisania, co oznacza, że wyniki wyrażenia muszą być r-wartościami.

Forma wyrażenia przyrostkowego

```cpp
simple-type-name ( expression-list )
```

wskazuje wywołanie konstruktora.  Jeśli simple-type-name jest typem podstawowym, lista wyrażeń musi być wyrażeniem pojedynczym, a to wyrażenie wskazuje rzutowanie wartości wyrażenia na typ podstawowy.  Ten typ wyrażenia rzutującego naśladuje konstruktor.  Jako że ta forma umożliwia konstruowanie podstawowych typów i klas przy użyciu tej samej składni, ta forma jest szczególnie przydatna podczas definiowania klas szablonów.

*Słowo kluczowe Cast* jest jednym z **`dynamic_cast`** , **`static_cast`** lub **`reinterpret_cast`** .  Więcej informacji można znaleźć w tematach [`dynamic_cast`](dynamic-cast-operator.md) [`static_cast`](static-cast-operator.md) i [`reinterpet_cast`](reinterpret-cast-operator.md) .

**`typeid`** Operator jest traktowany jako wyrażenie przyrostkowe.  Zobacz **Operator typeid**.

## <a name="formal-and-actual-arguments"></a>Argumenty formalne i rzeczywiste

Wywoływanie programów przekazuje informacje do wywołanych funkcji w „bieżących argumentach”. Wywołane funkcje mają dostęp do informacji za pomocą odpowiadających im „argumentów formalnych”.

Po wywołaniu funkcji, wykonywane są następujące zadania:

- Wszystkie rzeczywiste argumenty (dostarczane przez wywołującego) są obliczane. Nie ma niejawnego porządku, w którym argumenty są obliczane, ale wszystkie argumenty są obliczone i wszystkie efekty uboczne zakończone przed wejściem do funkcji.

- Każdy argument formalny jest inicjowany z odpowiadającym mu argumentem rzeczywistym na liście wyrażeń. (Formalny argument jest argumentem zadeklarowanym w nagłówku funkcji i używanym w treści funkcji). Konwersje są wykonywane tak jak w przypadku inicjalizacji — zarówno Konwersje standardowe, jak i zdefiniowane przez użytkownika są wykonywane w wyniku konwersji rzeczywistego argumentu na poprawny typ. Wykonywane inicjowanie zostało koncepcyjnie zilustrowane przez następujący kod:

    ```cpp
    void Func( int i ); // Function prototype
    ...
    Func( 7 );          // Execute function call
    ```

   Koncepcyjne inicjalizacje przed wywołaniem to:

    ```cpp
    int Temp_i = 7;
    Func( Temp_i );
    ```

   Należy zauważyć, że inicjalizacja jest wykonywana jakby przy użyciu składni znaku równości zamiast składni nawiasów. Kopia `i` została utworzona przed przekazaniem wartości do funkcji. (Aby uzyskać więcej informacji, zobacz [inicjatory](../cpp/initializers.md) i [konwersje](../cpp/user-defined-type-conversions-cpp.md)).

   W związku z tym, jeśli prototyp funkcji (Deklaracja) wywołuje argument typu **`long`** , a program wywołujący dostarcza rzeczywisty argument typu **`int`** , rzeczywisty argument zostanie podwyższony przy użyciu standardowej konwersji typu do typu **`long`** (zobacz [Konwersje standardowe](../cpp/standard-conversions.md)).

   Błędem jest podawanie rzeczywistego argumentu, dla którego nie ma żadnych standardowych lub zdefiniowanych przez użytkownika konwersji do typu argumentu formalnego.

   Dla rzeczywistych argumentów typu klasy, argument formalny jest inicjowany przez wywołanie konstruktora klasy. (Zobacz [konstruktory](../cpp/constructors-cpp.md) , aby uzyskać więcej informacji na temat tych specjalnych funkcji składowych klasy).

- Wywołanie funkcji jest wykonywane.

Poniższy fragment programu demonstruje wywołanie funkcji:

```cpp
// expre_Formal_and_Actual_Arguments.cpp
void func( long param1, double param2 );

int main()
{
    long i = 1;
    double j = 2;

    // Call func with actual arguments i and j.
    func( i, j );
}

// Define func with formal parameters param1 and param2.
void func( long param1, double param2 )
{
}
```

Gdy `func` jest wywoływana z Main, parametr formalny `param1` jest inicjowany z wartością `i` ( `i` jest konwertowany na typ **`long`** odpowiadający poprawnym typowi przy użyciu konwersji standardowej), a parametr formalny `param2` jest inicjowany z wartością `j` ( `j` jest konwertowana na typ **`double`** przy użyciu konwersji standardowej).

## <a name="treatment-of-argument-types"></a>Traktowanie typów argumentów

Nie można zmienić formalnych argumentów zadeklarowanych jako **`const`** typy w treści funkcji. Funkcje mogą zmieniać dowolny argument, który nie jest typu **`const`** . Jednak zmiana jest lokalna dla funkcji i nie ma wpływu na wartość rzeczywistego argumentu, chyba że rzeczywisty argument był odwołaniem do obiektu, który nie jest typu **`const`** .

Następujące funkcje ilustrują niektóre z tych koncepcji:

```cpp
// expre_Treatment_of_Argument_Types.cpp
int func1( const int i, int j, char *c ) {
   i = 7;   // C3892 i is const.
   j = i;   // value of j is lost at return
   *c = 'a' + j;   // changes value of c in calling function
   return i;
}

double& func2( double& d, const char *c ) {
   d = 14.387;   // changes value of d in calling function.
   *c = 'a';   // C3892 c is a pointer to a const object.
    return d;
}
```

## <a name="ellipsis-and-default-arguments"></a>Wielokropek i argumenty domyślne

Funkcje mogą być deklarowane w celu akceptowania mniejszej liczby argumentów niż określono w definicji funkcji, przy użyciu jednej z dwóch metod: wielokropka ( `...` ) lub argumentów domyślnych.

Wielokropek oznacza, że argumenty mogą być wymagane, ale liczba i typy nie są określone w deklaracji. Jest to zwykle niska Metoda programowania w języku C++, ponieważ obniża ona jedną z zalet języka C++: bezpieczeństwo typu. Różne konwersje są stosowane do funkcji zadeklarowanych za pomocą wielokropka niż w tych funkcjach, dla których są znane typy argumentów formalnych i rzeczywistych:

- Jeśli rzeczywisty argument jest typu **`float`** , zostanie podwyższony do typu **`double`** przed wywołaniem funkcji.

- Dowolny **`signed char`** lub **`unsigned char`** , **`signed short`** lub **`unsigned short`** , typ wyliczeniowy lub pole bitowe jest konwertowane na **`signed int`** lub **`unsigned int`** za pomocą promocji typu całkowitego.

- Każdy argument typu klasy jest przenoszona przez wartość jako strukturę danych; kopia jest tworzona przez kopiowanie binarne zamiast wywoływania konstruktora kopiującego klasy (jeśli taki istnieje).

Wielokropek, jeśli jest używany, musi być zadeklarowany jako ostatni na liście argumentów. Aby uzyskać więcej informacji na temat przekazywania zmiennej liczby argumentów, zobacz Omówienie [va_arg, va_start i va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) w *dokumentacji dotyczącej biblioteki wykonawczej*.

Aby uzyskać informacje na temat argumentów domyślnych w programowaniu środowiska CLR, zobacz [listy zmiennych argumentów (...) (C++/CLI)](../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

Argumenty domyślne umożliwiają określenie wartości argumentu, który ma zostać przyjęty, jeśli nie jest podany w wywołaniu funkcji. Poniższy fragment kodu pokazuje, jak działają argumenty domyślne. Aby uzyskać więcej informacji na temat ograniczeń dotyczących określania argumentów domyślnych, zobacz [argumenty domyślne](../cpp/default-arguments.md).

```cpp
// expre_Ellipsis_and_Default_Arguments.cpp
// compile with: /EHsc
#include <iostream>

// Declare the function print that prints a string,
// then a terminator.
void print( const char *string,
            const char *terminator = "\n" );

int main()
{
    print( "hello," );
    print( "world!" );

    print( "good morning", ", " );
    print( "sunshine." );
}

using namespace std;
// Define print.
void print( const char *string, const char *terminator )
{
    if( string != NULL )
        cout << string;

    if( terminator != NULL )
        cout << terminator;
}
```

Poprzedni program deklaruje funkcję, `print` która przyjmuje dwa argumenty. Jednak drugi argument, *terminator*, ma wartość domyślną `"\n"` . W programie `main` pierwsze dwa wywołania, aby `print` zezwolić na domyślny drugi argument do podania nowego wiersza, aby zakończyć wydrukowany ciąg. Trzecie wywołanie określa wartość jawną dla drugiego argumentu. Dane wyjściowe programu są

```Output
hello,
world!
good morning, sunshine.
```

## <a name="see-also"></a>Zobacz też

[Typy wyrażeń](../cpp/types-of-expressions.md)
