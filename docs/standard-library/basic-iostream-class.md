---
description: Dowiedz się więcej na temat klasy basic_iostream
title: basic_iostream — Klasa
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: c9b605c5eb36a0bc725ce21e2c89617357078d40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321517"
---
# <a name="basic_iostream-class"></a>basic_iostream — Klasa

Klasa strumienia, która może wykonywać zarówno dane wejściowe, jak i wyjściowe.

## <a name="syntax"></a>Składnia

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream : public basic_istream<Elem, Tr>,
    public basic_ostream<Elem, Tr>
{
public:
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};
```

## <a name="remarks"></a>Uwagi

Szablon klasy opisuje obiekt, który kontroluje wstawienia, poprzez jego klasę bazową [basic_ostream](../standard-library/basic-ostream-class.md) <  `Elem` , `Tr`> i wyodrębniania, za pomocą swojej klasy bazowej [basic_istream](../standard-library/basic-istream-class.md) <  `Elem` `Tr`>. Dwa obiekty współużytkują wspólną wirtualną klasę bazową [basic_ios](../standard-library/basic-ios-class.md) <  `Elem` , `Tr`>. Zarządzają one również wspólnym buforem strumieni z elementami typu `Elem` , których cechy znaku są określane przez klasę `Tr` . Konstruktor inicjuje swoje klasy podstawowe za pomocą `basic_istream` ( **strbuf**) i `basic_ostream` ( **strbuf**).

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[basic_iostream](#basic_iostream)|Utwórz `basic_iostream` obiekt.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[wymiany](#swap)|Wymienia zawartość podanego `basic_iostream` obiektu dla zawartości tego obiektu.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|-|-|
|[operator =](#op_eq)|Przypisuje wartość określonego `basic_iostream` obiektu do tego obiektu. Jest to przypisanie przenoszenia obejmujące element `rvalue` , który nie pozostawia kopii w tle.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<istream>

**Przestrzeń nazw:** std

## <a name="basic_iostreambasic_iostream"></a><a name="basic_iostream"></a> basic_iostream:: basic_iostream

Utwórz `basic_iostream` obiekt.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parametry

*strbuf*\
Istniejący `basic_streambuf` obiekt.

*Kliknij*\
Istniejący `basic_iostream` obiekt, który jest używany do utworzenia nowego `basic_iostream` .

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor inicjuje obiekty podstawowe w drodze do `basic_istream(strbuf)` i `basic_ostream(strbuf)` .

Drugi Konstruktor inicjuje obiekty podstawowe przez wywołanie `move(right)` .

## <a name="basic_iostreamoperator"></a><a name="op_eq"></a> basic_iostream:: operator =

Przypisz wartość określonego `basic_iostream` obiektu do tego obiektu. Jest to przypisanie przenoszenia obejmujące rvalue, które nie pozostawia kopii w tle.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
`rvalue`Odwołanie do `basic_iostream` obiektu, z którego ma zostać przypisane przypisanie.

### <a name="remarks"></a>Uwagi

Operator elementu członkowskiego wywołuje `swap(right)` .

## <a name="basic_iostreamswap"></a><a name="swap"></a> basic_iostream:: swap

Wymienia zawartość podanego `basic_iostream` obiektu dla zawartości tego obiektu.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
`basic_iostream`Obiekt do zamiany.

### <a name="remarks"></a>Uwagi

Funkcja elementu członkowskiego wywołuje `swap(right)` .

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)\
[Konwencje iostreams](../standard-library/iostreams-conventions.md)
