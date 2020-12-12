---
description: 'Dowiedz się więcej na temat: Klasa index'
title: index — Klasa
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 46b49a7e0f65f06ad64ed32367cdfe6f6ca5ed1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330048"
---
# <a name="index-class"></a>index — Klasa

Definiuje wektor indeksu *N*-wymiarowego.

## <a name="syntax"></a>Składnia

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>Parametry

*_Rank*<br/>
Ranga lub liczba wymiarów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor indeksów](#index_ctor)|Inicjuje nowe wystąpienie klasy `index`.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator--](#operator--)|Zmniejsza każdy element `index` obiektu.|
|[operator% =](#operator_mod_eq)|Oblicza moduł (resztę) każdego elementu w obiekcie, `index` gdy ten element jest podzielony przez liczbę.|
|[operator * =](#operator_star_eq)|Mnoży każdy element `index` obiektu przez liczbę.|
|[operator/=](#operator_div_eq)|Dzieli każdy element `index` obiektu przez liczbę.|
|[index:: operator\[\]](#operator_at)|Zwraca element, który znajduje się w określonym indeksie.|
|[operator + +](#operator_add_add)|Zwiększa każdy element `index` obiektu.|
|[operator + =](#operator_add_eq)|Dodaje określoną liczbę do każdego elementu `index` obiektu.|
|[operator =](#operator_eq)|Kopiuje zawartość określonego `index` obiektu do tego elementu.|
|[operator-=](#operator_-_eq)|Odejmuje określoną liczbę od każdego elementu `index` obiektu.|

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Stała rangi](#rank)|Przechowuje rangę `index` obiektu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`index`

## <a name="remarks"></a>Uwagi

`index`Struktura reprezentuje wektor współrzędnej *N* liczb całkowitych, który określa unikatową pozycję w przestrzeni *n*-wymiarowej. Wartości w wektorze są uporządkowane od najbardziej do najmniej znaczących. Wartości składników można pobrać przy użyciu [operatora =](#operator_eq).

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp. h

**Przestrzeń nazw:** Współbieżności

## <a name="index-constructor"></a><a name="index_ctor"></a> Konstruktor indeksów

Inicjuje nowe wystąpienie klasy index.

```cpp
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Array*<br/>
Jednowymiarowa tablica z wartościami rangi.

*_I*<br/>
Lokalizacja indeksu w indeksie jednowymiarowym.

*_I0*<br/>
Długość najbardziej znaczącego wymiaru.

*_I1*<br/>
Długość kolejnego najbardziej znaczącego wymiaru.

*_I2*<br/>
Długość najmniej znaczącego wymiaru.

*_Other*<br/>
Obiekt indeksu, na którym bazuje Nowy obiekt indeksu.

## <a name="operator--"></a><a name="operator--"></a> operator--

Zmniejsza każdy element obiektu index.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Wartości zwracane

Dla operatora prefiksu obiekt indeksu (* this). Dla operatora sufiksu nowy obiekt indeksu.

## <a name="operator"></a><a name="operator_mod_eq"></a> operator% =

Oblicza moduł (resztę) każdego elementu w obiekcie index, gdy ten element jest podzielony przez określoną liczbę.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
Liczba, która ma zostać podzielna przez w celu znalezienia modułu.

## <a name="return-value"></a>Wartość zwracana

Obiekt index.

## <a name="operator"></a><a name="operator_star_eq"></a> operator * =

Mnoży każdy element w obiekcie index przez określoną liczbę.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
Liczba do pomnożenia.

## <a name="operator"></a><a name="operator_div_eq"></a> operator/=

Dzieli każdy element w obiekcie index przez określoną liczbę.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
Liczba, przez którą ma zostać podzielona wartość.

## <a name="operator"></a><a name="operator_at"></a> zakład\[\]

Zwraca składnik indeksu w określonej lokalizacji.

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Index*<br/>
Liczba całkowita z zakresu od 0 do rangi minus 1.

### <a name="return-value"></a>Wartość zwracana

Element o określonym indeksie.

### <a name="remarks"></a>Uwagi

Poniższy przykład wyświetla wartości składnika indeksu.

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator"></a><a name="operator_add_add"></a> operator + +

Zwiększa każdy element obiektu index.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Wartość zwracana

Dla operatora prefiksu obiekt indeksu (* this). Dla operatora sufiksu nowy obiekt indeksu.

## <a name="operator"></a><a name="operator_add_eq"></a> operator + =

Dodaje określoną liczbę do każdego elementu obiektu index.

```cpp
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
Liczba, która ma zostać dodana.

### <a name="return-value"></a>Wartość zwracana

Obiekt index.

## <a name="operator"></a><a name="operator_eq"></a> operator =

Kopiuje zawartość określonego obiektu index do tego.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
Obiekt indeksu do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego obiektu indeksu.

## <a name="operator-"></a><a name="operator_-_eq"></a> operator-=

Odejmuje określoną liczbę od każdego elementu obiektu index.

```cpp
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
Liczba do odjęcia.

### <a name="return-value"></a>Wartość zwracana

Obiekt index.

## <a name="rank"></a><a name="rank"></a> Stopni

Pobiera rangę obiektu index.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
