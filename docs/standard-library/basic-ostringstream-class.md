---
description: Dowiedz się więcej na temat klasy basic_ostringstream
title: basic_ostringstream — Klasa
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: b745f6b733d093b620e15d0aa22593713988caf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325644"
---
# <a name="basic_ostringstream-class"></a>basic_ostringstream — Klasa

Opisuje obiekt, który kontroluje Wstawianie elementów i zakodowanych obiektów do buforu strumienia klasy [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **elem**, **TR** `Alloc`>.

## <a name="syntax"></a>Składnia

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametry

*Alokacj*\
Klasa alokatora.

*Elem*\
Typ podstawowego elementu ciągu.

*Zdawczy*\
Cechy znaków wyspecjalizowane dla elementu Basic ciągu.

## <a name="remarks"></a>Uwagi

Klasa opisuje obiekt, który kontroluje Wstawianie elementów i zakodowanych obiektów do buforu strumienia, z elementami typu `Elem` , których cechy znaku są określane przez klasę `Tr` , i których elementy są przydzielane przez Alokator klasy `Alloc` . Obiekt przechowuje obiekt klasy basic_stringbuf< **elem**, **TR**, `Alloc`>.

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Konstruuje obiekt typu `basic_ostringstream` .|

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[allocator_type](#allocator_type)|Typ jest synonimem dla *alokacji* parametru szablonu.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[rdbuf](#rdbuf)|Zwraca adres buforu zapisanego strumienia typu `pointer` do [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` , `Tr` , `Alloc`>.|
|[str](#str)|Ustawia lub pobiera tekst w buforze ciągów bez zmiany pozycji zapisu.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<sstream>

**Przestrzeń nazw:** std

## <a name="basic_ostringstreamallocator_type"></a><a name="allocator_type"></a> basic_ostringstream:: allocator_type

Typ jest synonimem dla *alokacji* parametru szablonu.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstreambasic_ostringstream"></a><a name="basic_ostringstream"></a> basic_ostringstream:: basic_ostringstream

Konstruuje obiekt typu basic_ostringstream.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametry

*_Mode*\
Jedno z wyliczeń w [ios_base:: openmode](../standard-library/ios-base-class.md#openmode).

*str*\
Obiekt typu `basic_string`.

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor inicjuje klasę bazową, wywołując [basic_ostream](../standard-library/basic-ostream-class.md)( **SB**), gdzie `sb` jest przechowywany obiekt klasy [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **elem**, **TR**, `Alloc`>. Inicjuje również **SB** przez wywołanie Basic_stringbuf< **elem**, **TR**, `Alloc`> ( `_Mode` &#124; `ios_base::out` ).

Drugi Konstruktor inicjuje klasę bazową, wywołując basic_ostream ( **SB**). Jest on również inicjowany `sb` przez wywołanie basic_stringbuf< **elem**, **TR**, `Alloc`> (_ *str*, `_Mode` &#124; `ios_base::out` ).

## <a name="basic_ostringstreamrdbuf"></a><a name="rdbuf"></a> basic_ostringstream:: rdbuf

Zwraca adres buforu zapisanego strumienia typu `pointer` do [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **elem**, **TR**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Wartość zwracana

Adres buforu zapisanego strumienia typu `pointer` do basic_stringbuf< **elem**, **TR**, `Alloc`>.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca adres przechowywanego bufora strumienia typu `pointer` do basic_stringbuf< **elem**, **TR**, `Alloc`>.

### <a name="example"></a>Przykład

Zobacz [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) , aby zapoznać się z przykładem, który używa `rdbuf` .

## <a name="basic_ostringstreamstr"></a><a name="str"></a> basic_ostringstream:: str

Ustawia lub pobiera tekst w buforze ciągów bez zmiany pozycji zapisu.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametry

*_Newstr*\
Nowy ciąg.

### <a name="return-value"></a>Wartość zwracana

Zwraca obiekt klasy [basic_string](../standard-library/basic-string-class.md) <  **elem**, **TR** `Alloc`>, którego kontrolowana sekwencja jest kopią sekwencji kontrolowanej przez **\* ten** element.

### <a name="remarks"></a>Uwagi

Pierwsza funkcja członkowska zwraca [rdbuf](#rdbuf)  ->  [str](../standard-library/basic-stringbuf-class.md#str). Druga funkcja członkowska wywołuje `rdbuf`  ->  **str**( `_Newstr` ).

### <a name="example"></a>Przykład

Zapoznaj się z przykładem [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) `str` .

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)\
[Konwencje iostreams](../standard-library/iostreams-conventions.md)
