---
description: 'Dowiedz się więcej na temat: platform:: WriteOnlyArray, Klasa'
title: 'Platform:: WriteOnlyArray, Klasa'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
helpviewer_keywords:
- Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
ms.openlocfilehash: cddbe0d3823ba7b9751bd60844d9ce699546b804
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307772"
---
# <a name="platformwriteonlyarray-class"></a>Platform:: WriteOnlyArray, Klasa

Reprezentuje tablicę jednowymiarową używaną jako parametr wejściowy, gdy obiekt wywołujący przekazuje tablicę dla metody do wypełnienia.

Ta klasa referencyjna jest zadeklarowana jako prywatna w vccorlib. h; w związku z tym nie jest emitowany w metadanych i można go używać tylko z C++. Ta klasa jest przeznaczona tylko do użycia jako parametr wejściowy, który odbiera tablicę przydzieloną przez wywołującego. Nie jest konstrukcyjną od kodu użytkownika. Umożliwia metodzie języka C++ zapis bezpośrednio w tej tablicy — wzorzec, który jest znany jako wzorzec *metodzie FillArray* . Aby uzyskać więcej informacji, zobacz [Array i WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="syntax"></a>Składnia

```cpp
private ref class WriteOnlyArray<T, 1>
```

### <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

Te metody mają wewnętrzny dostęp — to znaczy, że są dostępne tylko w aplikacji lub składniku C++.

|Nazwa|Opis|
|----------|-----------------|
|[WriteOnlyArray:: BEGIN](#begin)|Iterator, który wskazuje na pierwszy element tablicy.|
|[WriteOnlyArray::D ATA](#data)|Wskaźnik do buforu danych.|
|[WriteOnlyArray:: end](#end)|Iterator, który wskazuje jeden poza ostatnim elementem w tablicy.|
|[WriteOnlyArray:: FastPass](#fastpass)|Wskazuje, czy tablica może korzystać z mechanizmu FastPass, który jest optymalizacją niewidocznie wykonywaną przez system. Nie używaj tego w kodzie|
|[WriteOnlyArray:: length](#length)|Zwraca liczbę elementów w tablicy.|
|[WriteOnlyArray:: Set](#set)|Ustawia określony element na określoną wartość.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`WriteOnlyArray`

### <a name="requirements"></a>Wymagania

Opcja kompilatora: **/zw**

**Metadane:** Obiekt platform. winmd

**Przestrzeń nazw:** Platformach

## <a name="writeonlyarraybegin-method"></a><a name="begin"></a> WriteOnlyArray:: BEGIN — Metoda

Zwraca wskaźnik do pierwszego elementu w tablicy.

### <a name="syntax"></a>Składnia

```cpp
T* begin() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do pierwszego elementu w tablicy.

### <a name="remarks"></a>Uwagi

Ten iterator może być używany z algorytmami STL, takimi jak wykonywanie `std::sort` operacji na elementach tablicy.

## <a name="writeonlyarraydata-property"></a><a name="data"></a> WriteOnlyArray::D ATA — Właściwość

Wskaźnik do buforu danych.

### <a name="syntax"></a>Składnia

```cpp
property T* Data{
   T* get() const;
}
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do nieprzetworzonych bajtów tablicowych.

## <a name="writeonlyarrayend-method"></a><a name="end"></a> WriteOnlyArray:: end — Metoda

Zwraca wskaźnik do jednego z ostatnich elementów w tablicy.

### <a name="syntax"></a>Składnia

```cpp
T* end() const;
```

### <a name="return-value"></a>Wartość zwracana

Iterator wskaźnika do jednego z ostatnich elementów w tablicy.

### <a name="remarks"></a>Uwagi

Ten iterator może być używany z algorytmami STL do wykonywania operacji, takich jak `std::sort` w przypadku elementów tablicy.

## <a name="writeonlyarrayfastpass-property"></a><a name="fastpass"></a> WriteOnlyArray:: FastPass, właściwość

Wskazuje, czy można wykonać wewnętrzną optymalizację FastPass. Nie przeznaczony do użycia przez kod użytkownika.

### <a name="syntax"></a>Składnia

```cpp
property bool FastPass{
   bool get() const;
}
```

### <a name="return-value"></a>Wartość zwracana

Wartość logiczna wskazująca, czy tablica jest FastPass.

## <a name="writeonlyarrayget-method"></a><a name="get"></a> WriteOnlyArray:: Get — Metoda

Zwraca element o określonym indeksie.

### <a name="syntax"></a>Składnia

```cpp
T& get(unsigned int indexArg) const;
```

### <a name="parameters"></a>Parametry

*indexArg*<br/>
Indeks do użycia.

### <a name="return-value"></a>Wartość zwracana

## <a name="writeonlyarraylength-property"></a><a name="length"></a> WriteOnlyArray:: Length — właściwość

Zwraca liczbę elementów w tablicy przydzielonym przez obiekt wywołujący.

### <a name="syntax"></a>Składnia

```cpp
property unsigned int Length{
   unsigned int get() const;
}
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w tablicy.

## <a name="writeonlyarrayset-function"></a><a name="set"></a> WriteOnlyArray:: Set — funkcja

Ustawia określoną wartość w określonym indeksie w tablicy.

### <a name="syntax"></a>Składnia

```cpp
T& set(
   unsigned int indexArg,
   T valueArg);
```

### <a name="parameters"></a>Parametry

*indexArg*<br/>
Indeks elementu, który ma zostać ustawiony.

*valueArg*<br/>
Wartość, która ma zostać ustawiona na `indexArg` .

### <a name="return-value"></a>Wartość zwracana

Odwołanie do elementu, który został właśnie ustawiony.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat interpretowania wartości HRESULT, zobacz [struktury kodów błędów modelu COM](/windows/win32/com/structure-of-com-error-codes).

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](platform-namespace-c-cx.md)<br/>
[Tworzenie składników środowisko wykonawcze systemu Windows w języku C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
