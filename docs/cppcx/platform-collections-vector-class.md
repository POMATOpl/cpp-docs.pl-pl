---
description: 'Dowiedz się więcej o: platform:: Collections:: Vector, Klasa'
title: 'Platform:: Collections:: Vector, Klasa'
ms.date: 12/04/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
ms.openlocfilehash: b13221c6280e0e94572cb4b6710bb59fbd7db4c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221192"
---
# <a name="platformcollectionsvector-class"></a>Platform:: Collections:: Vector, Klasa

Reprezentuje sekwencyjną kolekcję obiektów, do których można uzyskać dostęp za pomocą indeksu. Implementuje [system Windows:: Foundation:: Collections:: IObservableVector](/uwp/api/windows.foundation.collections.iobservablevector-1) , aby pomóc w [powiązaniu danych](/windows/uwp/data-binding/data-binding-in-depth)XAML.

## <a name="syntax"></a>Składnia

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ elementów zawartych w obiekcie Vector.

*Adres*<br/>
Określa Predykat binarny do testowania równości z wartościami typu *T*. Wartość domyślna to `std::equal_to<T>` .

### <a name="remarks"></a>Uwagi

Dozwolone typy to:

1. integers

1. Klasa interfejsu ^

1. publiczna Klasa referencyjna ^

1. Struktura wartości

1. publiczna Klasa enum

Klasa **Vector** jest implementacją w języku C++ w ramach konkretnej implementacji interfejsu [Windows:: Foundation:: Collections:: IVector](/uwp/api/windows.foundation.collections.ivector-1) .

Jeśli spróbujesz użyć typu **wektora** w publicznej wartości zwracanej lub parametrze, zostanie zgłoszony błąd kompilatora C3986. Błąd można naprawić, zmieniając parametr lub typ wartości zwracanej na [Windows:: Foundation:: Collections:: IVector](/uwp/api/windows.foundation.collections.ivector-1). Aby uzyskać więcej informacji, zobacz [kolekcje (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Vector:: Vector](#ctor)|Inicjuje nowe wystąpienie klasy Vector.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Vector:: Append](#append)|Wstawia określony element po ostatnim elemencie w bieżącym wektorze.|
|[Vector:: Clear](#clear)|Usuwa wszystkie elementy w bieżącym wektorze.|
|[Vector:: First](#first)|Zwraca iterator, który określa pierwszy element w wektorze.|
|[Vector:: GetAt](#getat)|Pobiera element bieżącego wektora, który jest identifed przez określony indeks.|
|[Vector:: getwiele](#getmany)|Pobiera sekwencję elementów z bieżącego wektora, rozpoczynając od określonego indeksu.|
|[Vector:: GetView](#getview)|Zwraca widok tylko do odczytu wektora; oznacza to, że [platform:: Collections:: VectorView](../cppcx/platform-collections-vectorview-class.md).|
|[Vector:: IndexOf](#indexof)|Wyszukuje określony element w bieżącym wektorze, a jeśli go znaleziono, zwraca indeks elementu.|
|[Vector:: InsertAt](#insertat)|Wstawia określony element do bieżącego wektora w elemencie identyfikowanym przez określony indeks.|
|[Vector:: Zamień wszystkie](#replaceall)|Usuwa elementy z bieżącego wektora, a następnie wstawia elementy z określonej tablicy.|
|[Vector:: RemoveAt](#removeat)|Usuwa element identyfikowany przez określony indeks z bieżącego wektora.|
|[Vector:: RemoveAtEnd](#removeatend)|Usuwa element na końcu bieżącego wektora.|
|[Vector:: SetAt](#setat)|Przypisuje określoną wartość do elementu w bieżącym wektorze, który jest identyfikowany przez określony indeks.|
|[Vector:: size](#size)|Zwraca liczbę elementów w bieżącym obiekcie wektora.|

### <a name="events"></a>Zdarzenia

| Nazwa | Opis |
|--|--|
| zdarzenia [Windows:: Foundation:: Collection:: VectorChangedEventHandler \<T> ^ VectorChanged](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1) | Występuje po zmianie wektora. |

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Vector`

### <a name="requirements"></a>Wymagania

**Nagłówek:** Collection. h

**Przestrzeń nazw:** Platform:: Collections

## <a name="vectorappend-method"></a><a name="append"></a> Vector:: Append — Metoda

Wstawia określony element po ostatnim elemencie w bieżącym wektorze.

### <a name="syntax"></a>Składnia

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Parametry

*indeks*<br/>
Element, który ma zostać wstawiony do wektora. Typ *elementu* jest definiowany przez *T* TypeName.

## <a name="vectorclear-method"></a><a name="clear"></a> Vector:: Clear — Metoda

Usuwa wszystkie elementy w bieżącym wektorze.

### <a name="syntax"></a>Składnia

```cpp
virtual void Clear();
```

## <a name="vectorfirst-method"></a><a name="first"></a> Vector:: First — Metoda

Zwraca iterator, który wskazuje na pierwszy element w wektorze.

### <a name="syntax"></a>Składnia

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Wartość zwracana

Iterator, który wskazuje na pierwszy element w wektorze.

### <a name="remarks"></a>Uwagi

Wygodnym sposobem przechowywania iteratora zwracanego przez First () jest przypisanie wartości zwracanej do zmiennej, która jest zadeklarowana za pomocą **`auto`** słowa kluczowego odejmowania. Na przykład `auto x = myVector->First();`. Ten iterator zna długość kolekcji.

Gdy potrzebna jest para iteratorów do przekazania do funkcji STL, użyj bezpłatnych funkcji [Windows:: Foundation:: Collections:: BEGIN](../cppcx/begin-function.md) i [Windows:: Foundation:: Collections](../cppcx/end-function.md) :: end

## <a name="vectorgetat-method"></a><a name="getat"></a> Vector:: GetAt — Metoda

Pobiera element bieżącego wektora, który jest identifed przez określony indeks.

### <a name="syntax"></a>Składnia

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Parametry

*indeks*<br/>
Liczba całkowita bez znaku równa zero, która określa konkretny element w obiekcie Vector.

### <a name="return-value"></a>Wartość zwracana

Element określony przez parametr *index* . Typ elementu jest definiowany przez *T* TypeName.

## <a name="vectorgetmany-method"></a><a name="getmany"></a> Vector:: getwiele — Metoda

Pobiera sekwencję elementów z bieżącego wektora, rozpoczynając od określonego indeksu i kopiuje je do tablicy przydzielonej przez obiekt wywołujący.

### <a name="syntax"></a>Składnia

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Parametry

*Indeks*<br/>
Liczony od zera indeks początku elementów do pobrania.

*dest*<br/>
Przypisana przez wywołujący Tablica elementów, które zaczynają się od elementu określonego przez *startIndex* i kończą na ostatnim elemencie w wektorze.

### <a name="return-value"></a>Wartość zwracana

Liczba pobranych elementów.

### <a name="remarks"></a>Uwagi

Ta funkcja nie jest przeznaczona do użycia bezpośrednio przez kod klienta. Jest używana wewnętrznie w [funkcji to_vector](../cppcx/to-vector-function.md) , aby umożliwić wydajną konwersję platform:: Vector wystąpienia do instancji std:: Vector.

## <a name="vectorgetview-method"></a><a name="getview"></a> Vector:: GetView — metoda

Zwraca widok tylko do odczytu wektora; oznacza to, że IVectorView.

### <a name="syntax"></a>Składnia

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Wartość zwracana

Obiekt IVectorView.

## <a name="vectorindexof-method"></a><a name="indexof"></a> Vector:: IndexOf — Metoda

Wyszukuje określony element w bieżącym wektorze, a jeśli go znaleziono, zwraca indeks elementu.

### <a name="syntax"></a>Składnia

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Element do znalezienia.

*indeks*<br/>
Indeks (liczony od zera) elementu, jeśli zostanie znaleziona *wartość* parametru; w przeciwnym razie 0.

Parametr *index* ma wartość 0, jeśli element jest pierwszym elementem wektora lub nie znaleziono elementu. Jeśli zwracana wartość to **`true`** , element został znaleziony i jest pierwszym elementem; w przeciwnym razie element nie został znaleziony.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli określony element zostanie znaleziony; w przeciwnym razie **`false`** .

### <a name="remarks"></a>Uwagi

IndexOf używa elementu std:: find_if, aby znaleźć element. Niestandardowe typy elementów powinny w związku z tym przeciążać operator = = i! =, aby umożliwić porównywanie równości wymagane przez find_if.

## <a name="vectorinsertat-method"></a><a name="insertat"></a> Vector:: InsertAt — Metoda

Wstawia określony element do bieżącego wektora w elemencie identyfikowanym przez określony indeks.

### <a name="syntax"></a>Składnia

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Parametry

*indeks*<br/>
Liczba całkowita bez znaku równa zero, która określa konkretny element w obiekcie Vector.

*elementów*<br/>
Element do wstawienia do wektora w elemencie określonym przez *indeks*. Typ *elementu* jest definiowany przez *T* TypeName.

## <a name="vectorremoveat-method"></a><a name="removeat"></a> Vector:: RemoveAt — metoda

Usuwa element identyfikowany przez określony indeks z bieżącego wektora.

### <a name="syntax"></a>Składnia

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Parametry

*indeks*<br/>
Liczba całkowita bez znaku równa zero, która określa konkretny element w obiekcie Vector.

## <a name="vectorremoveatend-method"></a><a name="removeatend"></a> Vector:: RemoveAtEnd — Metoda

Usuwa element na końcu bieżącego wektora.

### <a name="syntax"></a>Składnia

```cpp
virtual void RemoveAtEnd();
```

## <a name="vectorreplaceall-method"></a><a name="replaceall"></a> Vector:: Zamień wszystkie — Metoda

Usuwa elementy z bieżącego wektora, a następnie wstawia elementy z określonej tablicy.

### <a name="syntax"></a>Składnia

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Parametry

*Genotyp*<br/>
Tablica obiektów, których typ jest definiowany przez *T* TypeName.

## <a name="vectorsetat-method"></a><a name="setat"></a> Vector:: SetAt — Metoda

Przypisuje określoną wartość do elementu w bieżącym wektorze, który jest identyfikowany przez określony indeks.

### <a name="syntax"></a>Składnia

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Parametry

*indeks*<br/>
Liczba całkowita bez znaku równa zero, która określa konkretny element w obiekcie Vector.

*elementów*<br/>
Wartość do przypisania do określonego elementu. Typ *elementu* jest definiowany przez *T* TypeName.

## <a name="vectorsize-method"></a><a name="size"></a> Vector:: size — Metoda

Zwraca liczbę elementów w bieżącym obiekcie wektora.

### <a name="syntax"></a>Składnia

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w bieżącym wektorze.

## <a name="vectorvector-constructor"></a><a name="ctor"></a> Vector:: Vector — Konstruktor

Inicjuje nowe wystąpienie klasy Vector.

### <a name="syntax"></a>Składnia

```cpp
Vector();

explicit Vector(unsigned int size);
Vector( unsigned int size, T value);
template <typename U> explicit Vector( const ::std::vector<U>& v);
template <typename U> explicit Vector( std::vector<U>&& v);

Vector( const T * ptr, unsigned int size);
template <size_t N> explicit Vector(const T(&arr)[N]);
template <size_t N> explicit Vector(const std::array<T, N>& a);
explicit Vector(const Array<T>^ arr);

template <typename InIt> Vector(InIt first, InIt last);
Vector(std::initializer_list<T> il);
```

### <a name="parameters"></a>Parametry

*z*<br/>
[Std:: Array](../standard-library/array-class-stl.md) , która zostanie użyta do zainicjowania wektora.

*Genotyp*<br/>
[Platform:: Array](../cppcx/platform-array-class.md) , która będzie używana do inicjowania wektora.

*InIt*<br/>
Typ kolekcji obiektów, który jest używany do inicjowania bieżącego wektora.

*II*<br/>
[Std:: initializer_list](../standard-library/initializer-list-class.md) obiektów typu *T* , które będą używane do inicjowania wektora.

*N*<br/>
Liczba elementów w kolekcji obiektów, które są używane do inicjowania bieżącego wektora.

*zmienia*<br/>
Liczba elementów w wektorze.

*wartość*<br/>
Wartość, która jest używana do inicjowania każdego elementu w bieżącym wektorze.

*v*<br/>
[Lvalues i rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) do [std:: Vector](../standard-library/vector-class.md) , który jest używany do inicjowania bieżącego wektora.

*ptr*<br/>
Wskaźnik do obiektu `std::vector` , który jest używany do inicjowania bieżącego wektora.

*pierwszego*<br/>
Pierwszy element w sekwencji obiektów, który jest używany do inicjowania bieżącego wektora. Typ *pierwszego* jest przekazywana przy użyciu *doskonałego przekazywania dalej*. Aby uzyskać więcej informacji, zobacz [rvalue Reference deklarator:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*ostatniego*<br/>
Ostatni element w sekwencji obiektów, który jest używany do inicjowania bieżącego wektora. Typ *ostatniego* jest przekazywana przy użyciu *doskonałego przekazywania dalej*. Aby uzyskać więcej informacji, zobacz [rvalue Reference deklarator:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Zobacz też

[Kolekcje (C++/CX)](collections-c-cx.md)<br/>
[Przestrzeń nazw platformy](platform-namespace-c-cx.md)<br/>
[Tworzenie składników środowisko wykonawcze systemu Windows w języku C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
