---
description: Dowiedz się więcej na temat klasy array_view
title: array_view — Klasa
ms.date: 11/04/2016
f1_keywords:
- array_view
- AMP/array_view
- AMP/Concurrency::array_view::array_view
- AMP/Concurrency::array_view::copy_to
- AMP/Concurrency::array_view::data
- AMP/Concurrency::array_view::discard_data
- AMP/Concurrency::array_view::get_extent
- AMP/Concurrency::array_view::get_ref
- AMP/Concurrency::array_view::get_source_accelerator_view
- AMP/Concurrency::array_view::refresh
- AMP/Concurrency::array_view::reinterpret_as
- AMP/Concurrency::array_view::section
- AMP/Concurrency::array_view::synchronize
- AMP/Concurrency::array_view::synchronize_async
- AMP/Concurrency::array_view::synchronize_to
- AMP/Concurrency::array_view::synchronize_to_async
- AMP/Concurrency::array_view::view_as
- AMP/Concurrency::array_view::rank
- AMP/Concurrency::array_view::extent
- AMP/Concurrency::array_view::source_accelerator_view
- AMP/Concurrency::array_view::value_type
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
ms.openlocfilehash: 170eb51a437fd56b9b9e74bb22e5b84d3478b4bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247881"
---
# <a name="array_view-class"></a>array_view — Klasa

Przedstawia widok N-wymiarowy dla danych przechowywanych w innym kontenerze.

## <a name="syntax"></a>Składnia

```cpp
template <
    typename value_type,
    int _Rank = 1
>
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;

template <
    typename value_type,
    int _Rank
>
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;
```

### <a name="parameters"></a>Parametry

*value_type*<br/>
Typ danych elementów w `array_view` obiekcie.

*_Rank*<br/>
Ranga `array_view` obiektu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor array_view](#ctor)|Inicjuje nowe wystąpienie klasy `array_view`. Brak domyślnego konstruktora dla `array<T,N>` . Wszystkie konstruktory są ograniczone do uruchamiania tylko na procesorze CPU i nie można ich wykonać na obiekcie docelowym Direct3D.|
|[~ array_view destruktor](#ctor)|Niszczy `array_view` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[copy_to](#copy_to)|Kopiuje zawartość `array_view` obiektu do określonego miejsca docelowego przez wywołanie metody `copy(*this, dest)` .|
|[data](#data)|Zwraca wskaźnik do danych pierwotnych `array_view` .|
|[discard_data](#discard_data)|Odrzuca bieżące dane bazowe tego widoku.|
|[get_extent](#get_extent)|Zwraca obiekt zakresu obiektu array_view.|
|[get_ref](#get_ref)|Zwraca odwołanie do indeksowanego elementu.|
|[get_source_accelerator_view](#get_source_accelerator_view)|Zwraca [accelerator_view](accelerator-view-class.md) , w którym znajduje się źródło danych `array_view` .|
|[odowieżenie](#refresh)|Powiadamia `array_view` obiekt, że jego pamięć związana została zmodyfikowana poza `array_view` interfejsem. Wywołanie tej metody renderuje wszystkie nieodświeżone informacje w pamięci podręcznej.|
|[reinterpret_as](#reinterpret_as)|Zwraca tablicę jednowymiarową, która zawiera wszystkie elementy w `array_view` obiekcie.|
|[Paragraf](#section)|Zwraca podsekcję `array_view` obiektu, który znajduje się w określonej lokalizacji i opcjonalnie ma określony zakres.|
|[synchronize](#synchronize)|Synchronizuje wszelkie zmiany wprowadzone do `array_view` obiektu z powrotem do jego danych źródłowych.|
|[synchronize_async](#synchronize_async)|Asynchronicznie synchronizuje wszelkie modyfikacje wprowadzone do `array_view` obiektu z powrotem do jego danych źródłowych.|
|[synchronize_to](#synchronize_to)|Synchronizuje wszelkie modyfikacje wprowadzone do `array_view` obiektu do określonego [accelerator_view](accelerator-view-class.md).|
|[synchronize_to_async](#synchronize_to_async)|Asynchronicznie synchronizuje wszelkie modyfikacje wprowadzone do `array_view` obiektu do określonego [accelerator_view](accelerator-view-class.md).|
|[view_as](#view_as)|Tworzy `array_view` obiekt o różnej rangi przy użyciu `array_view` danych tego obiektu.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator ()](#operator_call)|Zwraca wartość elementu, który jest określony przez parametr lub parametry.|
|[zakład\[\]](#operator_at)|Zwraca element, który jest określony przez parametry.|
|[operator =](#operator_eq)|Kopiuje zawartość określonego `array_view` obiektu do tego elementu.|

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Stała rangi](#rank)|Przechowuje rangę `array_view` obiektu.|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[rozmiaru](#extent)|Pobiera `extent` obiekt, który definiuje kształt `array_view` obiektu.|
|[source_accelerator_view](#source_accelerator_view)|Pobiera [accelerator_view](accelerator-view-class.md) , w którym znajduje się źródło danych `array_view`|
|[value_type](#value_type)|Typ wartości `array_view` i powiązanej tablicy.|

## <a name="remarks"></a>Uwagi

`array_view`Klasa reprezentuje widok danych znajdujących się w obiekcie [Array](array-class.md) lub podsekcji `array` obiektu.

Możesz uzyskać dostęp do `array_view` obiektu, w którym znajdują się dane źródłowe (lokalnie) lub z innego akceleratora lub domeny spójności (zdalnie). Gdy uzyskujesz dostęp do obiektu zdalnie, widoki są kopiowane i zapisywane w pamięci podręcznej w razie potrzeby. Z wyjątkiem efektów automatycznej pamięci podręcznej `array_view` obiekty mają profil wydajności podobny do tego `array` obiektów. Podczas uzyskiwania dostępu do danych za pomocą widoków występuje niewielkie obniżenie wydajności.

Istnieją trzy scenariusze użycia zdalnego:

- Widok wskaźnika pamięci systemowej jest przesyłany za pomocą wywołania [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) akceleratora i dostępu do akceleratora.

- Widok tablicy w akceleratorze jest przesyłany przez `parallel_for_each` wywołanie do innego akceleratora i jest dostępny w tym miejscu.

- Dostęp do tablicy znajdującej się w akceleratorze znajduje się na tym samym PROCESORze.

W każdym z tych scenariuszy widoki, do których istnieją odwołania, są kopiowane przez środowisko uruchomieniowe do lokalizacji zdalnej i, jeśli są modyfikowane przez wywołania do `array_view` obiektu, są kopiowane z powrotem do lokalizacji lokalnej. Środowisko uruchomieniowe może zoptymalizować proces kopiowania zmian z powrotem, może spowodować skopiowanie tylko zmienionych elementów lub skopiowanie niezmienionych fragmentów. Nakładające się `array_view` na siebie obiekty w jednym źródle danych nie są gwarantowane, aby zachować integralność referencyjną w lokalizacji zdalnej.

Należy zsynchronizować dowolny dostęp wielowątkowy do tego samego źródła danych.

Środowisko wykonawcze zapewnia następujące gwarancje dotyczące buforowania danych w `array_view` obiektach:

- Wszystkie dobrze zsynchronizowane dostępy do `array` obiektu i `array_view` obiektu na nim w kolejności programu zgodnie z przypisaniem szeregowym — przed relacją.

- Wszystkie dobrze zsynchronizowane dostęp do nakładających się `array_view` obiektów na tym samym akceleratorze na pojedynczym `array` obiekcie są aliasem za pomocą `array` obiektu. Powodują one łączną liczbę wystąpień — przed relacją, która przestrzega kolejności programu. Brak buforowania. Jeśli `array_view` obiekty są wykonywane na różnych akceleratorach, kolejność dostępu jest niezdefiniowana, tworząc sytuację wyścigu.

Podczas tworzenia `array_view` obiektu za pomocą wskaźnika w pamięci systemowej, należy zmienić `array_view` obiekt widoku tylko za pośrednictwem `array_view` wskaźnika. Alternatywnie, należy wywołać `refresh()` jeden z `array_view` obiektów, które są dołączone do wskaźnika systemowego, jeśli podstawowa pamięć macierzysta jest zmieniana bezpośrednio, a nie za pomocą `array_view` obiektu.

Każda akcja powiadamia `array_view` obiekt, że bazowa pamięć natywna została zmieniona i że wszystkie kopie, które znajdują się na akceleratorze, są nieaktualne. Jeśli przestrzegasz tych wytycznych, widoki oparte na wskaźniku są identyczne z tymi, które są dostarczane do widoków tablic danych równoległych.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp. h

**Przestrzeń nazw:** Współbieżności

## <a name="array_view"></a><a name="dtor"></a> ~ array_view

Niszczy `array_view` obiekt.

```cpp
~array_view()restrict(amp,cpu);
```

## <a name="array_view"></a><a name="ctor"></a> array_view

Inicjuje nowe wystąpienie klasy `array_view`.

```cpp
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view& _Other)restrict(amp,cpu);

explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    _Container& _Src) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    int _E0,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _Container& _Src);

explicit array_view(
    int _E0,
    _In_ value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    _In_ value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _In_ value_type* _Src)restrict(amp,cpu);

array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const _Container& _Src) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    const _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    int _E0,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    int _E2,
    const _Container& _Src);

array_view(
    int _E0,
    const value_type* _Src)restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    const value_type* _Src) restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    int _E2,
    const value_type* _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Arr_type*<br/>
Typ elementu tablicy stylu C, z którego dane są dostarczane.

*_Container*<br/>
Argument szablonu, który musi określać kontener liniowy, który obsługuje `data()` i `size()` składowe.

*_E0*<br/>
Najbardziej znaczący składnik zakresu tej sekcji.

*_E1*<br/>
Najbardziej znaczący składnik zakresu tej sekcji.

*_E2*<br/>
Najmniej znaczący składnik zakresu tej sekcji.

*_Extent*<br/>
Zakres w każdym wymiarze `array_view` .

*_Other*<br/>
Obiekt typu `array_view<T,N>` , z którego ma zostać zainicjowany nowy `array_view` .

*_Size*<br/>
Rozmiar tablicy w stylu języka C, z której są dostarczane dane.

*_Src*<br/>
Wskaźnik do danych źródłowych, które zostaną skopiowane do nowej tablicy.

## <a name="copy_to"></a><a name="copy_to"></a> copy_to

Kopiuje zawartość `array_view` obiektu do określonego obiektu docelowego przez wywołanie `copy(*this, dest)` .

```cpp
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Parametry

*_Dest*<br/>
Obiekt do skopiowania.

## <a name="data"></a><a name="data"></a> Data

Zwraca wskaźnik do danych pierwotnych `array_view` .

```cpp
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do danych pierwotnych `array_view` .

## <a name="discard_data"></a><a name="discard_data"></a> discard_data

Odrzuca bieżące dane bazowe tego widoku. Jest to Wskazówka dotycząca optymalizacji dla środowiska uruchomieniowego użyta w celu uniknięcia kopiowania bieżącej zawartości widoku do elementu docelowego `accelerator_view` , na którym jest on dostępny, a jego użycie jest zalecane, jeśli istniejąca zawartość nie jest wymagana. Ta metoda jest No-op, gdy jest używana w kontekście ograniczenia (amp)

```cpp
void discard_data() const restrict(cpu);
```

## <a name="extent"></a><a name="extent"></a> rozmiaru

Pobiera `extent` obiekt, który definiuje kształt `array_view` obiektu.

```cpp
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

## <a name="get_extent"></a><a name="get_extent"></a> get_extent

Zwraca obiekt [zakresu](extent-class.md) `array_view` obiektu.

```cpp
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>Wartość zwracana

`extent`Obiekt `array_view` obiektu

## <a name="get_ref"></a><a name="get_ref"></a> get_ref

Pobierz odwołanie do elementu indeksowanego przez _Index. W przeciwieństwie do innych operatorów indeksowania na potrzeby uzyskiwania dostępu do array_view w PROCESORze, ta metoda nie powoduje niejawnego synchronizowania zawartości tej array_view z PROCESORem. Po uzyskaniu dostępu do array_view w lokalizacji zdalnej lub wykonaniu operacji kopiowania obejmującej tego array_view użytkownicy są odpowiedzialni za jawne zsynchronizowanie array_view z PROCESORem przed wywołaniem tej metody. Niewykonanie tej czynności spowoduje niezdefiniowane zachowanie.

```cpp
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```

### <a name="parameters"></a>Parametry

*_Index*<br/>
Indeks.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do elementu indeksowanego przez _Index

## <a name="get_source_accelerator_view"></a><a name="get_source_accelerator_view"></a> get_source_accelerator_view

Zwraca accelerator_view, w którym znajduje się źródło danych array_view. Jeśli array_view nie ma źródła danych, ten interfejs API zgłasza runtime_exception

```cpp
accelerator_view get_source_accelerator_view() const;
```

### <a name="return-value"></a>Wartość zwracana

## <a name="operator"></a><a name="operator_call"></a> operator ()

Zwraca wartość elementu, który jest określony przez parametr lub parametry.

```cpp
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Index*<br/>
Lokalizacja elementu.

*_I0*<br/>
Indeks w pierwszym wymiarze.

*_I1*<br/>
Indeks w drugim wymiarze.

*_I2*<br/>
Indeks w trzecim wymiarze.

*_I*<br/>
Lokalizacja elementu.

### <a name="return-value"></a>Wartość zwracana

Wartość elementu, który jest określony przez parametr lub parametry.

## <a name="operator"></a><a name="operator_at"></a> operator []

Zwraca element, który jest określony przez parametry.

```cpp
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Index*<br/>
Indeks.

*_I*<br/>
Indeks.

### <a name="return-value"></a>Wartość zwracana

Wartość elementu w indeksie lub `array_view` przewidywana w najbardziej znaczącym wymiarze.

## <a name="operator"></a><a name="operator_eq"></a> operator =

Kopiuje zawartość określonego `array_view` obiektu do tego elementu.

```cpp
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
`array_view`Obiekt, z którego mają zostać skopiowane.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego `array_view` obiektu.

## <a name="rank"></a><a name="rank"></a> stopni

Przechowuje rangę `array_view` obiektu.

```cpp
static const int rank = _Rank;
```

## <a name="refresh"></a><a name="refresh"></a> odowieżenie

Powiadamia `array_view` obiekt, że jego pamięć związana została zmodyfikowana poza `array_view` interfejsem. Wywołanie tej metody renderuje wszystkie nieodświeżone informacje w pamięci podręcznej.

```cpp
void refresh() const restrict(cpu);
```

## <a name="reinterpret_as"></a><a name="reinterpret_as"></a> reinterpret_as

Reinterpretuje array_view za pomocą jednowymiarowego array_view, co może mieć inny typ wartości niż array_view źródłowa.

### <a name="syntax"></a>Składnia

```cpp
template <
    typename _Value_type2
>
array_view< _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);

template <
    typename _Value_type2
>
array_view<const _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Value_type2*<br/>
Typ danych nowego `array_view` obiektu.

### <a name="return-value"></a>Wartość zwracana

`array_view`Obiekt lub obiekt const, `array_view` który jest oparty na tym `array_view` , z typem elementu przekonwertowanym z `T` na `_Value_type2` , a rangą zmniejszoną od *N* do 1.

### <a name="remarks"></a>Uwagi

Czasami warto wyświetlić tablicę wielowymiarową jako liniową, jednowymiarową tablicę, która może mieć inny typ wartości niż tablica źródłowa. Można to osiągnąć `array_view` za pomocą tej metody.

**Ostrzeżenie** Reinterpretacja obiektu array_view przy użyciu innego typu wartości jest potencjalnie niebezpieczną operacją. Ta funkcja powinna być używana z opieką.

Oto przykład:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

## <a name="section"></a><a name="section"></a> Paragraf

Zwraca podsekcję `array_view` obiektu, który znajduje się w określonej lokalizacji i opcjonalnie ma określony zakres.

```cpp
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _E0) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _I1,
    int _I2,
    int _E0,
    int _E1,
    int _E2) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_E0*<br/>
Najbardziej znaczący składnik zakresu tej sekcji.

*_E1*<br/>
Najbardziej znaczący składnik zakresu tej sekcji.

*_E2*<br/>
Najmniej znaczący składnik zakresu tej sekcji.

*_Ext*<br/>
Obiekt [zakresu](extent-class.md) , który określa zakres sekcji. Początek jest równy 0.

*_Idx*<br/>
Obiekt [index](index-class.md) , który określa lokalizację pochodzenia. Podsekcja jest resztą zakresu.

*_I0*<br/>
Najbardziej znaczący składnik pochodzenia tej sekcji.

*_I1*<br/>
Najbardziej znaczący składnik pochodzenia tej sekcji.

*_I2*<br/>
Najmniej znaczący składnik pochodzenia tej sekcji.

*_Rank*<br/>
Ranga sekcji.

*_Section_extent*<br/>
Obiekt [zakresu](extent-class.md) , który określa zakres sekcji.

*_Section_origin*<br/>
Obiekt [index](index-class.md) , który określa lokalizację pochodzenia.

### <a name="return-value"></a>Wartość zwracana

Podsekcja `array_view` obiektu, który znajduje się w określonym miejscu pochodzenia i, opcjonalnie, ma określony zakres. Gdy tylko `index` obiekt jest określony, podsekcja zawiera wszystkie elementy w skojarzonym zakresie, które mają indeksy, które są większe niż indeksy elementów w `index` obiekcie.

## <a name="source_accelerator_view"></a><a name="source_accelerator_view"></a> source_accelerator_view

Pobiera accelerator_view źródłowe, z którym skojarzona jest ta array_view.

```cpp
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

## <a name="synchronize"></a><a name="synchronize"></a> Zsynchronizuj

Synchronizuje wszelkie zmiany wprowadzone do `array_view` obiektu z powrotem do jego danych źródłowych.

```cpp
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>Parametry

*_Access_type*<br/>
Zamierzone [access_type](concurrency-namespace-enums-amp.md#access_type) na [accelerator_view](accelerator-view-class.md)docelowym. Ten parametr ma wartość domyślną `access_type_read` .

## <a name="synchronize_async"></a><a name="synchronize_async"></a> synchronize_async

Asynchronicznie synchronizuje wszelkie modyfikacje wprowadzone do `array_view` obiektu z powrotem do jego danych źródłowych.

```cpp
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>Parametry

*_Access_type*<br/>
Zamierzone [access_type](concurrency-namespace-enums-amp.md#access_type) na [accelerator_view](accelerator-view-class.md)docelowym. Ten parametr ma wartość domyślną `access_type_read` .

### <a name="return-value"></a>Wartość zwracana

Przyszłość, na której należy poczekać na zakończenie operacji.

## <a name="synchronize_to"></a><a name="synchronize_to"></a> synchronize_to

Synchronizuje wszelkie modyfikacje wprowadzone w tym array_view do określonego accelerator_view.

```cpp
void synchronize_to(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Parametry

*_Accl_view*<br/>
Docelowy accelerator_view do synchronizowania.

*_Access_type*<br/>
Żądany access_type na accelerator_view docelowym. Ten parametr ma wartość domyślną access_type_read.

## <a name="synchronize_to_async"></a><a name="synchronize_to_async"></a> synchronize_to_async

Asynchronicznie synchronizuje wszelkie modyfikacje wprowadzone do tej array_view do określonego accelerator_view.

```cpp
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Parametry

*_Accl_view*<br/>
Docelowy accelerator_view do synchronizowania.

*_Access_type*<br/>
Żądany access_type na accelerator_view docelowym. Ten parametr ma wartość domyślną access_type_read.

### <a name="return-value"></a>Wartość zwracana

Przyszłość, na której należy poczekać na zakończenie operacji.

## <a name="value_type"></a><a name="value_type"></a> value_type

Typ wartości array_view i powiązanej tablicy.

```cpp
typedef typenamevalue_type value_type;
```

## <a name="view_as"></a><a name="view_as"></a> view_as

Interpretuje ją `array_view` jako `array_view` inną rangę.

```cpp
template <
    int _New_rank
>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

template <
    int _New_rank
>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_New_rank*<br/>
Ranga nowego `array_view` obiektu.

*_View_extent*<br/>
Zmiana kształtu `extent` .

*value_type*<br/>
Typ danych elementów w oryginalnym obiekcie [Array](array-class.md) i zwracanym `array_view` obiekcie.

### <a name="return-value"></a>Wartość zwracana

`array_view`Obiekt, który jest skonstruowany.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
