---
title: Operatory &lt;bitset&gt;
ms.date: 11/04/2016
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.openlocfilehash: 23c6abffe7e433a0550c45502a12e9adaf652a33
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416789"
---
# <a name="ltbitsetgt-operators"></a>Operatory &lt;bitset&gt;

## <a name="op_amp"></a>&amp; operatora

Wykonuje `AND` bitowe między dwoma bitsets.

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametry

\ *lewo*
Pierwszy z dwóch bitsets, których odpowiednie elementy mają być połączone z `AND`bitowe.

*prawa*\
Drugi z dwóch valarrays, których odpowiednie elementy mają być połączone z `AND`bitowe.

### <a name="return-value"></a>Wartość zwrócona

Bitset, których elementy są wynikiem wykonywania operacji `AND` na odpowiednich elementach *lewej* i *prawej*.

### <a name="example"></a>Przykład

```cpp
// bitset_and.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 & b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0001
```

## <a name="op_lt_lt"></a>&lt;operatora &lt;

Wstawia tekstową reprezentację sekwencji bitowej do strumienia wyjściowego.

```cpp
template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>Parametry

*prawa*\
Obiekt typu **bitset\<N >** , który ma zostać wstawiony do strumienia wyjściowego jako ciąg.

### <a name="return-value"></a>Wartość zwrócona

Tekstowa reprezentacja sekwencji bitowej w `ostr`.

### <a name="remarks"></a>Uwagi

Funkcja szablonu przeciąża `operator<<`, co umożliwia zapisanie bitset bez uprzedniego przekonwertowania na ciąg. Funkcja szablonu skutecznie wykonuje:

`ostr << right.`[to_string](bitset-class.md)`<CharType, Traits, allocator<CharType>>()`

### <a name="example"></a>Przykład

```cpp
// bitset_op_insert.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 9 );

   // bitset inserted into output stream directly
   cout << "The ordered set of bits in the bitset<5> b1(9)"
        << "\n can be output with the overloaded << as: ( "
        << b1 << " )" << endl;

   // Compare converting bitset to a string before
   // inserting it into the output steam
   string s1;
   s1 =  b1.template to_string<char,
      char_traits<char>, allocator<char> >( );
   cout << "The string returned from the bitset b1"
        << "\n by the member function to_string( ) is: "
        << s1 << "." << endl;
}
```

## <a name="op_gt_gt"></a>&gt;operatora &gt;

Odczytuje ciąg znaków bitowych w bitset.

```cpp
template <class CharType, class Traits, size_t Bits>
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>& i_str,
    bitset<N>& right);
```

### <a name="parameters"></a>Parametry

*i_str*\
Ciąg wprowadzony w strumieniu wejściowym, który ma zostać wstawiony do bitset.

*prawa*\
Bitset, który otrzymuje bity ze strumienia wejściowego.

### <a name="return-value"></a>Wartość zwrócona

Funkcja szablonu zwraca ciąg *i_str*.

### <a name="remarks"></a>Uwagi

Funkcja szablonu przeciąża `operator>>`, aby przechowywać ją w bitset *prawej* `bitset(str)`wartości, gdzie `str` jest obiektem typu [basic_string](basic-string-class.md)`< CharType, Traits, allocator< CharType > >&` wyodrębnionym z *i_str*.

Funkcja szablonu wyodrębnia elementy z *i_str* i wstawia je do bitset do momentu:

- Wszystkie elementy bitowe zostały wyodrębnione ze strumienia wejściowego i przechowywane w bitset.

- Bitset jest uzupełniona o bity ze strumienia wejściowego.

- Napotkano element wejściowy, który nie ma wartości 0 ani 1.

### <a name="example"></a>Przykład

```cpp
#include <bitset>
#include <iostream>
#include <string>

using namespace std;
int main()
{

   bitset<5> b1;
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"
        << "Try bit string of length less than or equal to 5,\n"
        << " (for example: 10110): ";
   cin >>  b1;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<5> b1 as: ( "
        << b1 << " )" << endl;

   // Truncation due to longer string of bits than length of bitset
   bitset<2> b3;
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"
        << " Try bit string of length greater than 2,\n"
        << " (for example: 1011): ";
   cin >>  b3;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<2> b3 as: ( "
        << b3 << " )" << endl;

   // Flushing the input stream
   char buf[100];
   cin.getline(&buf[0], 99);

   // Truncation with non-bit value
   bitset<5> b2;
   cout << "Enter a string for input into  bitset<5>.\n"
        << " that contains a character than is NOT a 0 or a 1,\n "
        << " (for example: 10k01): ";
   cin >>  b2;

   cout << "The string entered from the keyboard\n"
        << " has been input into bitset<5> b2 as: ( "
        << b2 << " )" << endl;
}
```

## <a name="op_xor"></a>operator ^

Wykonuje `EXCLUSIVE-OR` bitowe między dwoma bitsets.

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametry

\ *lewo*
Pierwszy z dwóch bitsets, których odpowiednie elementy mają być połączone z `EXCLUSIVE-OR`bitowe.

*prawa*\
Drugi z dwóch valarrays, których odpowiednie elementy mają być połączone z `EXCLUSIVE-OR`bitowe.

### <a name="return-value"></a>Wartość zwrócona

Bitset, których elementy są wynikiem wykonywania operacji `EXCLUSIVE-OR` na odpowiednich elementach *lewej* i *prawej*.

### <a name="example"></a>Przykład

```cpp
// bitset_xor.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 ^ b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0110
```

## <a name="op_or"></a>zakład&#124;

Wykonuje `OR` bitowe między dwoma bitsets.

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametry

\ *lewo*
Pierwszy z dwóch bitsets, których odpowiednie elementy mają być połączone z `OR`bitowe.

*prawa*\
Drugi z dwóch valarrays, których odpowiednie elementy mają być połączone z `OR`bitowe.

### <a name="return-value"></a>Wartość zwrócona

Bitset, których elementy są wynikiem wykonywania operacji `OR` na odpowiednich elementach *lewej* i *prawej*.

### <a name="example"></a>Przykład

```cpp
// bitset_or.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 | b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0111
```
