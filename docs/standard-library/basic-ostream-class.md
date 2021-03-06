---
description: Dowiedz się więcej na temat klasy basic_ostream
title: basic_ostream — Klasa
ms.date: 03/27/2019
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
ms.openlocfilehash: 19bcc5fddd7ae73a77492f88ed516beb03182839
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325657"
---
# <a name="basic_ostream-class"></a>basic_ostream — Klasa

Ten szablon klasy opisuje obiekt, który kontroluje Wstawianie elementów i zakodowanych obiektów do buforu strumienia z elementami typu `Elem` , znanym również jako [char_type](../standard-library/basic-ios-class.md#char_type), których cechy znaku są określane przez klasę `Tr` , znane także jako [traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Składnia

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parametry

*Elem*\
Klasa `char_type`.

*Zdawczy*\
Znak `traits_type` .

## <a name="remarks"></a>Uwagi

Większość funkcji Członkowskich, które [<<operator ](#basic_ostream_operator_lt_lt) przeciążania, są formatowanymi funkcjami wyjściowymi. Są one zgodne ze wzorcem:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{try
{<convert and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

Dwie inne funkcje członkowskie są niesformatowanymi funkcjami wyjściowymi. Są one zgodne ze wzorcem:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
{try
{<obtain and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

Obie grupy funkcji wywołuje metodę [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**), Jeśli napotkają błąd podczas wstawiania elementów.

Obiekt klasy basic_istream \< **Elem**, **Tr**> przechowuje tylko wirtualny, publiczny obiekt podstawowy klasy [basic_ios](../standard-library/basic-ios-class.md) **\<Elem**, **Tr>** .

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [klasy basic_ofstream](../standard-library/basic-ofstream-class.md) , aby dowiedzieć się więcej o strumieniach wyjściowych.

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[basic_ostream](#basic_ostream)|Konstruuje `basic_ostream` obiekt.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[opróżnianie](#flush)|Opróżnia bufor.|
|[Ubrani](#put)|Umieszcza znak w strumieniu.|
|[seekp](#seekp)|Resetuje pozycję w strumieniu wyjściowym.|
|[WartownikDźwięków](#sentry)|Klasa zagnieżdżona opisuje obiekt, którego struktura deklaracji ma sformatowane funkcje wyjściowe i niesformatowane funkcje wyjściowe.|
|[wymiany](#swap)|Wymienia wartości tego `basic_ostream` obiektu dla podanego `basic_ostream` obiektu.|
|[tellp](#tellp)|Pozycja raportów w strumieniu wyjściowym.|
|[write (zapis)](#write)|Umieszcza znaki w strumieniu.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|-|-|
|[operator =](#op_eq)|Przypisuje wartość podanego `basic_ostream` parametru obiektu do tego obiektu.|
|[<<operatora ](#basic_ostream_operator_lt_lt)|Zapisuje dane w strumieniu.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<ostream>

**Przestrzeń nazw:** std

## <a name="basic_ostreambasic_ostream"></a><a name="basic_ostream"></a> basic_ostream:: basic_ostream

Konstruuje `basic_ostream` obiekt.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Parametry

*strbuf*\
Obiekt typu [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*\
**`true`** Jeśli jest to strumień standardowy; w przeciwnym razie **`false`** .

*Kliknij*\
Odwołanie rvalue do obiektu typu `basic_ostream` .

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor inicjuje klasę bazową, wywołując metodę [init](../standard-library/basic-ios-class.md#init)( `strbuf` ). Drugi Konstruktor inicjuje klasę bazową, wywołując [basic_ios:: Move](../standard-library/basic-ios-class.md#move) `(right)` .

### <a name="example"></a>Przykład

Aby dowiedzieć się więcej o strumieniach wyjściowych, zobacz przykład dla [basic_ofstream:: basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) .

## <a name="basic_ostreamflush"></a><a name="flush"></a> basic_ostream:: Flush

Opróżnia bufor.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu basic_ostream.

### <a name="remarks"></a>Uwagi

Jeśli [rdbuf](../standard-library/basic-ios-class.md#rdbuf) nie jest pustym wskaźnikiem, funkcja wywołuje **rdbuf->** [pubsync](../standard-library/basic-streambuf-class.md#pubsync). Jeśli zwraca wartość-1, funkcja wywołuje metodę [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**). Zwraca **\* to**.

### <a name="example"></a>Przykład

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt"></a> basic_ostream:: operator&lt;&lt;

Zapisuje dane w strumieniu.

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>Parametry

*PFN*\
Wskaźnik funkcji.

*strbuf*\
Wskaźnik do `stream_buf` obiektu.

*użyte*\
Element do zapisu w strumieniu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu basic_ostream.

### <a name="remarks"></a>Uwagi

\<ostream>Nagłówek definiuje również kilka globalnych operatorów wstawiania. Aby uzyskać więcej informacji, zobacz [operator<<](../standard-library/ostream-operators.md#op_lt_lt).

Pierwsza funkcja członkowska gwarantuje, że wyrażenie formularza `ostr << endl` wywołuje [endl](../standard-library/ostream-functions.md#endl)**(ostr)**, a następnie zwraca **\* to**. Drugie i trzecie funkcje zapewniają, że inne manipulowania, takie jak [szesnastkowo](../standard-library/ios-functions.md#hex), zachowują się podobnie. Pozostałe funkcje to wszystkie sformatowane funkcje wyjściowe.

Funkcja

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

wyodrębnia elementy z *strbuf*, jeśli *strbuf* nie jest wskaźnikiem null i wstawia je. Wyodrębnianie kończy się na końcu pliku lub jeśli wyodrębnianie zgłasza wyjątek (który jest ponownie zgłaszany). Zatrzymuje również, bez wyodrębniania elementu, w przypadku niepowodzenia wstawiania. Jeśli funkcja nie wstawia żadnych elementów lub jeśli wyodrębnianie zgłasza wyjątek, funkcja wywołuje metodę [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). W każdym przypadku funkcja zwraca **\* ten** wynik.

Funkcja

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

Konwertuje `_Val` do pola Boolean i wstawia je przez wywołanie [use_facet](../standard-library/basic-filebuf-class.md#open) **<num_put \<Elem, OutIt>** `(` [getloc](../standard-library/ios-base-class.md#getloc)). [Put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\* this**, `getloc` , **Val**). Tutaj, `OutIt` został zdefiniowany jako [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md) **\<Elem, Tr>** . Funkcja zwraca **\* ten** wynik.

Funkcje

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

Każda Konwertuj wartość *Val* na pole liczbowe i Wstaw ją, wywołując **use_facet<num_put \<Elem, OutIt>**( `getloc` ). **Put**(**OutIt**( `rdbuf` ), **\* this**, `getloc` , **Val**). Tutaj **OutIt** jest definiowana jako **ostreambuf_iterator \<Elem, Tr>**. Funkcja zwraca **\* ten** wynik.

Funkcje

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

Każda Konwertuj wartość *Val* do pola liczbowego i Wstaw ją, wywołując **use_facet<\<Elem, OutIt> num_put**( `getloc` )**. Put**(**OutIt**( `rdbuf` ), **\* this**, `getloc` **Val**). Tutaj **OutIt** jest definiowana jako **ostreambuf_iterator \<Elem, Tr>**. Funkcja zwraca **\* ten** wynik.

### <a name="example"></a>Przykład

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="basic_ostreamoperator"></a><a name="op_eq"></a> basic_ostream:: operator =

Przypisuje wartości dla podanego `basic_ostream` parametru obiektu do tego obiektu.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
`rvalue`Odwołanie do `basic_ostream` obiektu.

### <a name="remarks"></a>Uwagi

Operator elementu członkowskiego wywołuje zamianę `(right)` .

## <a name="basic_ostreamput"></a><a name="put"></a> basic_ostream::p UT

Umieszcza znak w strumieniu.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Parametry

*_Ch*\
Znak.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu basic_ostream.

### <a name="remarks"></a>Uwagi

Niesformatowana funkcja wyjściowa wstawia element *_Ch*. Zwraca **\* to**.

### <a name="example"></a>Przykład

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="basic_ostreamseekp"></a><a name="seekp"></a> basic_ostream:: seekp

Resetowanie pozycji w strumieniu wyjściowym.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Parametry

*_Pos*\
Pozycja w strumieniu.

*_Off*\
Przesunięcie względem *_Way*.

*_Way*\
Jeden z [ios_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Enumerations.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu basic_ostream.

### <a name="remarks"></a>Uwagi

Jeśli to [się nie powiedzie](../standard-library/basic-ios-class.md#fail) **`false`** , Pierwsza funkcja członkowska wywołuje **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*) dla niektórych `pos_type` obiektów tymczasowych `newpos` . Jeśli `fail` ma wartość false, druga funkcja wywołuje **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*). W obu przypadkach, jeśli ( `off_type` )**newpos = =** ( `off_type` ) (-1) (operacja pozycjonowania zakończy się niepowodzeniem), funkcja wywołuje **ISTR.** [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Obie funkcje zwracają **\* ten**.

### <a name="example"></a>Przykład

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="basic_ostreamsentry"></a><a name="sentry"></a> basic_ostream:: Sentry

Klasa zagnieżdżona opisuje obiekt, którego struktura deklaracji ma sformatowane funkcje wyjściowe i niesformatowane funkcje wyjściowe.

Klasa Sentry {Public: Explicit Sentry (basic_ostream \<Elem, Tr>& _Ostr); operator bool () const; ~ Sentry ();};

### <a name="remarks"></a>Uwagi

Klasa zagnieżdżona opisuje obiekt, którego struktura deklaracji ma sformatowane funkcje wyjściowe i niesformatowane funkcje wyjściowe. Jeśli **ostr.** [dobre](../standard-library/basic-ios-class.md#good) **`true`** i **ostr.** [powiązanie](../standard-library/basic-ios-class.md#tie) nie jest wskaźnikiem o wartości null, Konstruktor wywołuje **ostr. krawat->** [Flush](#flush). Następnie Konstruktor przechowuje wartość zwracaną przez `ostr.good` `status` . Późniejsze wywołanie w celu `operator bool` dostarczenia tej przechowywanej wartości.

Jeśli `uncaught_exception` Funkcja Returns **`false`** i [flags](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) ma wartość różną od zera, destruktor wywołuje [opróżnianie](#flush).

## <a name="basic_ostreamswap"></a><a name="swap"></a> basic_ostream:: swap

Wymienia wartości tego `basic_ostream` obiektu dla wartości podanej `basic_ostream` .

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Odwołanie do `basic_ostream` obiektu.

### <a name="remarks"></a>Uwagi

Funkcja członkowska wywołuje [basic_ios:: swap](../standard-library/basic-ios-class.md#swap) `(right)` , aby wymienić zawartość tego obiektu na zawartość z *prawej strony*.

## <a name="basic_ostreamtellp"></a><a name="tellp"></a> basic_ostream:: tellp

Pozycja raportu w strumieniu wyjściowym.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Wartość zwracana

Pozycja w strumieniu wyjściowym.

### <a name="remarks"></a>Uwagi

Jeśli to [się nie powiedzie](../standard-library/basic-ios-class.md#fail) **`false`** , funkcja członkowska zwraca [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` , **w**). W przeciwnym razie zwraca `pos_type` (-1).

### <a name="example"></a>Przykład

Zobacz [seekp](#seekp) , aby zapoznać się z przykładem `tellp` .

## <a name="basic_ostreamwrite"></a><a name="write"></a> basic_ostream:: Write

Umieszczanie znaków w strumieniu.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Parametry

*liczbą*\
Liczba znaków, które mają zostać umieszczone w strumieniu.

*str*\
Znaki, które mają zostać umieszczone w strumieniu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu basic_ostream.

### <a name="remarks"></a>Uwagi

[Niesformatowana funkcja wyjściowa](../standard-library/basic-ostream-class.md) wstawia sekwencję elementów *Count* , zaczynając od *str*.

### <a name="example"></a>Przykład

Zobacz [dane StreamSize](../standard-library/ios-typedefs.md#streamsize) , aby zapoznać się z przykładem `write` .

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)\
[Konwencje iostreams](../standard-library/iostreams-conventions.md)
