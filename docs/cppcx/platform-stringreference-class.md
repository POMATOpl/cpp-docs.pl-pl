---
description: 'Dowiedz się więcej na temat: platform:: StringReference, Klasa'
title: 'Platform:: StringReference, Klasa'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
ms.openlocfilehash: 5c211776bccbd3ba2fedaf769502f7dad71b6eb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307954"
---
# <a name="platformstringreference-class"></a>Platform:: StringReference, Klasa

Typ optymalizacji, który służy do przekazywania danych ciągu z `Platform::String^` parametrów wejściowych do innych metod przy minimalnych operacjach kopiowania.

## <a name="syntax"></a>Składnia

```cpp
class StringReference
```

### <a name="remarks"></a>Uwagi

### <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[StringReference::StringReference](#ctor)|Dwa konstruktory do tworzenia wystąpień `StringReference` .|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[StringReference::D ATA](#data)|Zwraca dane ciągu jako tablicę wartości char16.|
|[StringReference:: length](#length)|Zwraca liczbę znaków w ciągu.|
|[StringReference::GetHSTRING](#gethstring)|Zwraca dane ciągu jako HSTRING.|
|[StringReference:: GetString](#getstring)|Zwraca dane ciągu jako `Platform::String^` .|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[StringReference:: operator =](#operator-assign)|Przypisuje `StringReference` do nowego `StringReference` wystąpienia.|
|[StringReference:: operator ()](#operator-call)|Konwertuje `StringReference` do `Platform::String^` .|

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Nagłówek:** vccorlib. h

## <a name="stringreferencedata-method"></a><a name="data"></a> StringReference::D ATA — Metoda

Zwraca zawartość tego elementu `StringReference` jako tablicę wartości char16.

### <a name="syntax"></a>Składnia

```cpp
const ::default::char16 * Data() const;
```

### <a name="return-value"></a>Wartość zwracana

Tablica znaków UNICODE char16.

## <a name="stringreferencegethstring-method"></a><a name="gethstring"></a> StringReference:: GetHSTRING, Metoda

Zwraca zawartość ciągu jako `__abi_HSTRING` .

### <a name="syntax"></a>Składnia

```cpp
__abi_HSTRING GetHSTRING() const;
```

### <a name="return-value"></a>Wartość zwracana

`__abi_HSTRING`Zawierający dane ciągu.

### <a name="remarks"></a>Uwagi

## <a name="stringreferencegetstring-method"></a><a name="getstring"></a> StringReference:: GetString — Metoda

Zwraca zawartość ciągu jako `Platform::String^` .

### <a name="syntax"></a>Składnia

```cpp
__declspec(no_release_return) __declspec(no_refcount)
    ::Platform::String^ GetString() const;
```

### <a name="return-value"></a>Wartość zwracana

A `Platform::String^` , który zawiera dane ciągu.

## <a name="stringreferencelength-method"></a><a name="length"></a> StringReference:: length — Metoda

Zwraca liczbę znaków w ciągu.

### <a name="syntax"></a>Składnia

```cpp
unsigned int Length() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba całkowita bez znaku, która określa liczbę znaków w ciągu.

### <a name="remarks"></a>Uwagi

## <a name="stringreferenceoperator-operator"></a><a name="operator-assign"></a> StringReference:: operator = — operator

Przypisuje określony obiekt do bieżącego `StringReference` obiektu.

### <a name="syntax"></a>Składnia

```cpp
StringReference& operator=(const StringReference& __fstrArg);
StringReference& operator=(const ::default::char16* __strArg);
```

### <a name="parameters"></a>Parametry

*__fstrArg*<br/>
Adres `StringReference` obiektu, który jest używany do inicjowania bieżącego `StringReference` obiektu.

*__strArg*<br/>
Wskaźnik do tablicy wartości Char16, który jest używany do inicjowania bieżącego `StringReference` obiektu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu typu `StringReference` .

### <a name="remarks"></a>Uwagi

Ponieważ `StringReference` jest klasą standardowego języka C++, a nie klasą referencyjną, nie jest ona wyświetlana w **Przeglądarka obiektów**.

## <a name="stringreferenceoperator--operator"></a><a name="operator-call"></a> StringReference:: operator () — operator

Konwertuje `StringReference` obiekt na `Platform::String^` obiekt.

### <a name="syntax"></a>Składnia

```cpp
__declspec(no_release_return) __declspec(no_refcount)
         operator ::Platform::String^() const;
```

### <a name="return-value"></a>Wartość zwracana

Dojście do obiektu typu `Platform::String` .

## <a name="stringreferencestringreference-constructor"></a><a name="ctor"></a> StringReference:: StringReference — Konstruktor

Inicjuje nowe wystąpienie klasy `StringReference`.

### <a name="syntax"></a>Składnia

```cpp
StringReference();
StringReference(const StringReference& __fstrArg);
StringReference(const ::default::char16* __strArg);
StringReference(const ::default::char16* __strArg, size_t __lenArg);
```

### <a name="parameters"></a>Parametry

*__fstrArg*<br/>
`StringReference`Których dane są używane do inicjowania nowego wystąpienia.

*__strArg*<br/>
Wskaźnik do tablicy wartości Char16, który jest używany do inicjowania nowego wystąpienia.

*__lenArg*<br/>
Liczba elementów w `__strArg` .

### <a name="remarks"></a>Uwagi

Pierwsza wersja tego konstruktora jest konstruktorem domyślnym. Druga wersja Inicjuje nową `StringReference` klasę wystąpienia z obiektu, który jest określony przez `__fstrArg` parametr. Trzecie i czwarte przeciążenia inicjują nowe `StringReference` wystąpienie z tablicy wartości char16. char16 reprezentuje 16-bitowy znak tekstowy w formacie UNICODE.

## <a name="see-also"></a>Zobacz też

[Platform:: StringReference, Klasa](../cppcx/platform-stringreference-class.md)
