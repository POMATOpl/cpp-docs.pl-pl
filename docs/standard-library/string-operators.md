---
title: '&lt;operatory ciągów&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: fef2eb784eca9c9eabbdcd727b051d5c2a4ccfd2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376647"
---
# <a name="ltstringgt-operators"></a>&lt;operatory ciągów&gt;

||||
|-|-|-|
|[operator!=](#op_neq)|[Operator&gt;](#op_gt)|[Operator&gt;&gt;](#op_gt_gt)|
|[Operator&gt;=](#op_gt_eq)|[Operator&lt;](#op_lt)|[Operator&lt;&lt;](#op_lt_lt)|
|[Operator&lt;=](#op_lt_eq)|[operator+](#op_add)|[operator==](#op_eq_eq)|

## <a name="operator"></a><a name="op_add"></a>operator+

Łączy dwa obiekty ciągu.

```cpp
template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do połączenia.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do połączenia.

### <a name="return-value"></a>Wartość zwracana

Ciąg, który jest łączenie ciągów wejściowych.

### <a name="remarks"></a>Uwagi

Funkcje każdego `operator+` przeciążenia, aby połączyć dwa obiekty szablonu klasy [basic_string Class](../standard-library/basic-string-class.md). Wszystko skutecznie `basic_string< CharType, Traits, Allocator>(Left).append(right)`wrócić . Aby uzyskać więcej informacji, zobacz [dołączanie](../standard-library/basic-string-class.md#append).

### <a name="example"></a>Przykład

```cpp
// string_op_con.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "anti" );
   string s2 ( "gravity" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "heroine";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // Declaring a character constant
   char c1 = '!';
   cout << "The character constant c1 = " << c1 << "." << endl;

   // First member function: concatenates an  object
   // of type basic_string with an object of type basic_string
   string s12 = s1 + s2;
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;

   // Second & fourth member functions: concatenate an object
   // of type basic_string with an object of C-syle string type
   string s1s3 = s1 + s3;
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;

   // Third & fifth member functions: concatenate an object
   // of type basic_string with a character constant
   string s1s3c1 = s1s3 + c1;
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;
}
```

```Output
The basic_string s1 = anti.
The basic_string s2 = gravity.
The C-style string s3 = heroine.
The character constant c1 = !.
The string concatenating s1 & s2 is: antigravity
The string concatenating s1 & s3 is: antiheroine
The string concatenating s1 & s3 is: antiheroine!
```

## <a name="operator"></a><a name="op_neq"></a>operator!=

Sprawdza, czy obiekt ciągu po lewej stronie operatora nie jest równy obiektowi ciągu po prawej stronie.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

### <a name="return-value"></a>Wartość zwracana

**true,** jeśli obiekt ciągu po lewej stronie operatora nie jest leksykograficznie równy obiektowi ciągu po prawej stronie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

Porównanie między obiektami ciągów opiera się na parowym porównaniem leksykograficznym ich znaków. Dwa ciągi są równe, jeśli mają taką samą liczbę znaków, a ich odpowiednie wartości znaków są takie same. W przeciwnym razie są nierówne.

### <a name="example"></a>Przykład

```cpp
// string_op_ne.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 != s2 )
      cout << "The strings s1 & s2 are not equal." << endl;
   else
      cout << "The strings s1 & s2 are equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 != s3 )
      cout << "The strings s1 & s3 are not equal." << endl;
   else
      cout << "The strings s1 & s3 are equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 != s2 )
      cout << "The strings s3 & s2 are not equal." << endl;
   else
      cout << "The strings s3 & s2 are equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a>operator==

Sprawdza, czy obiekt ciągu po lewej stronie operatora jest równy obiektowi ciągu po prawej stronie.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

### <a name="return-value"></a>Wartość zwracana

**true,** jeśli obiekt ciągu po lewej stronie operatora jest leksykograficznie równy obiektowi ciągu po prawej stronie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

Porównanie między obiektami ciągów opiera się na parowym porównaniem leksykograficznym ich znaków. Dwa ciągi są równe, jeśli mają taką samą liczbę znaków, a ich odpowiednie wartości znaków są takie same. W przeciwnym razie są nierówne.

### <a name="example"></a>Przykład

```cpp
// string_op_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 == s2 )
      cout << "The strings s1 & s2 are equal." << endl;
   else
      cout << "The strings s1 & s2 are not equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 == s3 )
      cout << "The strings s1 & s3 are equal." << endl;
   else
      cout << "The strings s1 & s3 are not equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 == s2 )
      cout << "The strings s3 & s2 are equal." << endl;
   else
      cout << "The strings s3 & s2 are not equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a>Operator&lt;

Sprawdza, czy obiekt ciągu po lewej stronie operatora jest mniejsza niż do obiektu ciągu po prawej stronie.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

### <a name="return-value"></a>Wartość zwracana

**true,** jeśli obiekt ciągu po lewej stronie operatora jest leksykograficznie mniej niż obiekt ciągu po prawej stronie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

Leksykograficzne porównanie ciągów porównuje ich charakter według znaków, aż do:

- Znajduje dwa odpowiednie znaki nierówne, a wynik ich porównania jest traktowany jako wynik porównania ciągów.

- Nie znajduje żadnych nierówności, ale jeden ciąg ma więcej znaków niż inne, a krótszy ciąg jest uważany za mniej niż dłuższy ciąg.

- Nie znajduje żadnych nierówności i stwierdza, że ciągi mają taką samą liczbę znaków, a więc ciągi są równe.

### <a name="example"></a>Przykład

```cpp
// string_op_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 < s2 )
      cout << "The string s1 is less than the string s2." << endl;
   else
      cout << "The string s1 is not less than the string s2." << endl;

   // Second member function: comparison between left-hand object
   // of type basic_string & right-hand object of C-syle string type
   if ( s1 < s3 )
      cout << "The string s1 is less than the string s3." << endl;
   else
      cout << "The string s1 is not less than the string s3." << endl;

   // Third member function: comparison between left-hand object
   // of C-syle string type & right-hand object of type basic_string
   if ( s3 < s2 )
      cout << "The string s3 is less than the string s2." << endl;
   else
      cout << "The string s3 is not less than the string s2." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than the string s2.
The string s1 is not less than the string s3.
The string s3 is less than the string s2.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Operator&lt;=

Sprawdza, czy obiekt ciągu po lewej stronie operatora jest mniejszy lub równy obiektowi ciągu po prawej stronie.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

### <a name="return-value"></a>Wartość zwracana

**true,** jeśli obiekt ciągu po lewej stronie operatora jest leksykograficznie mniejszy lub równy obiektowi ciągu po prawej stronie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

Leksykograficzne porównanie ciągów porównuje ich charakter według znaków, aż do:

- Znajduje dwa odpowiednie znaki nierówne, a wynik ich porównania jest traktowany jako wynik porównania ciągów.

- Nie znajduje żadnych nierówności, ale jeden ciąg ma więcej znaków niż inne, a krótszy ciąg jest uważany za mniej niż dłuższy ciąg.

- Nie znajduje żadnych nierówności i stwierdza, że ciągi mają taką samą liczbę znaków, więc ciągi są równe.

### <a name="example"></a>Przykład

```cpp
// string_op_le.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 <= s2 )
      cout << "The string s1 is less than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 <= s3 )
      cout << "The string s1 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s3." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type  & right-side object of type basic_string
   if ( s2 <= s3 )
      cout << "The string s2 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than or equal to the string s2.
The string s1 is less than or equal to the string s3.
The string s2 is greater than the string s3.
```

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Operator&lt;&lt;

Funkcja szablonu, która zapisuje ciąg do strumienia wyjściowego.

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametry

*_Ostr*\
Strumień wyjściowy zapisywany do.

*Str*\
Ciąg, który ma zostać wprowadzony do strumienia wyjściowego.

### <a name="return-value"></a>Wartość zwracana

Zapisuje wartość określonego ciągu do strumienia wyjściowego *_Ostr*.

### <a name="remarks"></a>Uwagi

Funkcja szablonu przeciąża **operatora<<** wstawianie *str* obiektu szablonu klasy [basic_string](../standard-library/basic-string-class.md) do strumienia * \_Ostr*. Funkcja skutecznie `_Ostr.write( str.c_str, str.size )`zwraca .

## <a name="operatorgt"></a><a name="op_gt"></a>Operator&gt;

Sprawdza, czy obiekt ciągu po lewej stronie operatora jest większy niż do obiektu ciągu po prawej stronie.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

### <a name="return-value"></a>Wartość zwracana

**true,** jeśli obiekt ciągu po lewej stronie operatora jest leksykograficznie większy niż obiekt ciągu po prawej stronie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

Leksykograficzne porównanie ciągów porównuje ich charakter według znaków, aż do:

- Znajduje dwa odpowiednie znaki nierówne, a wynik ich porównania jest traktowany jako wynik porównania ciągów.

- Nie znajduje żadnych nierówności, ale jeden ciąg ma więcej znaków niż inne, a krótszy ciąg jest uważany za mniej niż dłuższy ciąg.

- Nie znajduje żadnych nierówności i stwierdza, że ciągi mają taką samą liczbę znaków, a więc ciągi są równe.

### <a name="example"></a>Przykład

```cpp
// string_op_gt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 > s2 )
      cout << "The string s1 is greater than "
           << "the string s2." << endl;
   else
      cout << "The string s1 is not greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 > s1 )
      cout << "The string s3 is greater than "
           << "the string s1." << endl;
   else
      cout << "The string s3 is not greater than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 > s3 )
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
   else
      cout << "The string s2 is not greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is not greater than the string s2.
The string s3 is greater than the string s1.
The string s2 is greater than the string s3.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Operator&gt;=

Sprawdza, czy obiekt ciągu po lewej stronie operatora jest większa lub równa obiektowi ciągu po prawej stronie.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Lewej*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

*Prawo*\
Ciąg w stylu C lub `basic_string` obiekt typu do porównania.

### <a name="return-value"></a>Wartość zwracana

**true,** jeśli obiekt ciągu po lewej stronie operatora jest leksykograficznie większy lub równy obiektowi ciągu po prawej stronie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

Leksykograficzne porównanie ciągów porównuje ich charakter według znaków, aż do:

- Znajduje dwa odpowiednie znaki nierówne, a wynik ich porównania jest traktowany jako wynik porównania ciągów.

- Nie znajduje żadnych nierówności, ale jeden ciąg ma więcej znaków niż inne, a krótszy ciąg jest uważany za mniej niż dłuższy ciąg.

- Nie znajduje żadnych nierówności i stwierdza, że ciągi mają taką samą liczbę znaków, a więc ciągi są równe.

### <a name="example"></a>Przykład

```cpp
// string_op_ge.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 >= s2 )
      cout << "The string s1 is greater than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is less than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 >= s1 )
      cout << "The string s3 is greater than or equal to "
           << "the string s1." << endl;
   else
      cout << "The string s3 is less than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 >= s3 )
      cout << "The string s2 is greater than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is less than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is less than the string s2.
The string s3 is greater than or equal to the string s1.
The string s2 is greater than or equal to the string s3.
```

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>Operator&gt;&gt;

Funkcja szablonu, która odczytuje ciąg ze strumienia wejściowego.

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*_Istr*\
Strumień wejściowy używany do wyodrębniania sekwencji

*Prawo*\
Ciąg, który jest wyodrębniany ze strumienia wejściowego.

### <a name="return-value"></a>Wartość zwracana

Odczytuje wartość określonego ciągu z *_Istr* i zwraca go w *prawo*.

### <a name="remarks"></a>Uwagi

Operator pomija początkowe białe spacje, chyba że flaga jest ustawiona. `skipws` Odczytuje wszystkie następujące znaki, dopóki następny znak jest biały znak lub koniec pliku zostanie osiągnięty.

Funkcja szablonu przeciąża **operatora>>,** aby zastąpić sekwencję kontrolowaną *przez prawo* sekwencją elementów wyodrębnionych ze strumienia *_Istr*. Ograniczniki ekstrakcji:

- Na końcu pliku.

- Po wyodrębnienia `_Istr`funkcji . **szerokość,** jeśli ta wartość jest niezerowa.

Po wyodrębnienia `_Istr`funkcji . [max_size](../standard-library/basic-string-class.md#max_size) elementy.

- Po funkcji wyodrębnia element *ch,* dla którego [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **CharType**> >( `getloc`). **jest**( **ctype** \< **CharType**>:: **spacja**, *ch*) jest true, w którym to przypadku znak jest odłożony.

Jeśli funkcja nie wyodrębnia żadnych elementów, wywołuje [setstate](../standard-library/basic-ios-class.md#setstate)(`ios_base::failbit`). W każdym razie, to wywołuje **istr**. **szerokości**(0) \* i zwraca **tę wartość**.

### <a name="example"></a>Przykład

```cpp
// string_op_read_.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string c0;
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";
   cin >> c0;
   cout << "The string entered is c0 = " << c0 << endl;
}
```

## <a name="see-also"></a>Zobacz też

[\<>ciągu](../standard-library/string.md)
