---
description: 'Dowiedz się więcej na temat: Klasa CSimpleArray'
title: Klasa CSimpleArray
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: 95750662587c7ab47500a338c3ecd7e74a92eb34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140793"
---
# <a name="csimplearray-class"></a>Klasa CSimpleArray

Ta klasa udostępnia metody zarządzania prostą tablicą.

## <a name="syntax"></a>Składnia

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych do przechowywania w tablicy.

*TEqual*<br/>
Obiekt cech, definiujący test równości dla elementów typu *T*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|Konstruktor dla prostej tablicy.|
|[CSimpleArray:: ~ CSimpleArray](#dtor)|Destruktor dla prostej tablicy.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleArray:: Add](#add)|Dodaje nowy element do tablicy.|
|[CSimpleArray:: find](#find)|Znajduje element w tablicy.|
|[CSimpleArray:: GetData](#getdata)|Zwraca wskaźnik do danych przechowywanych w tablicy.|
|[CSimpleArray:: GetSize](#getsize)|Zwraca liczbę elementów przechowywanych w tablicy.|
|[CSimpleArray:: Remove](#remove)|Usuwa dany element z tablicy.|
|[CSimpleArray::](#removeall)|Usuwa wszystkie elementy z tablicy.|
|[CSimpleArray::RemoveAt](#removeat)|Usuwa określony element z tablicy.|
|[CSimpleArray:: Setatindex —](#setatindex)|Ustawia określony element w tablicy.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleArray:: operator\[\]](#operator_at)|Pobiera element z tablicy.|
|[CSimpleArray:: operator =](#operator_eq)|Operator przypisania.|

## <a name="remarks"></a>Uwagi

`CSimpleArray` zapewnia metody tworzenia prostej tablicy o dowolnym typie i zarządzania nią `T` .

Parametr `TEqual` zawiera sposób definiowania funkcji równości dla dwóch elementów typu `T` . Tworząc klasę podobną do [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), można zmienić zachowanie testu równości dla danej tablicy. Na przykład podczas pracy z tablicą wskaźników przydatne może być zdefiniowanie równości w zależności od wartości odniesienia wskaźników. Domyślna implementacja używa **operatora = ()**.

Zarówno `CSimpleArray` , jak i [CSimpleMap](../../atl/reference/csimplemap-class.md) , są przeznaczone dla niewielkiej liczby elementów. [CAtlArray](../../atl/reference/catlarray-class.md) i [CAtlMap](../../atl/reference/catlmap-class.md) należy używać, gdy tablica zawiera dużą liczbę elementów.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsimpcoll. h

## <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a> CSimpleArray:: Add

Dodaje nowy element do tablicy.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>Parametry

*&*<br/>
Element, który ma zostać dodany do tablicy.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli element został pomyślnie dodany do tablicy, w przeciwnym razie FALSE.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a> CSimpleArray::CSimpleArray

Konstruktor dla obiektu Array.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>Parametry

*src*<br/>
Istniejący `CSimpleArray` obiekt.

### <a name="remarks"></a>Uwagi

Inicjuje składowe danych, tworząc nowy pusty `CSimpleArray` obiekt lub kopię istniejącego `CSimpleArray` obiektu.

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a> CSimpleArray:: ~ CSimpleArray

Destruktor.

```
~CSimpleArray();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

## <a name="csimplearrayfind"></a><a name="find"></a> CSimpleArray:: find

Znajduje element w tablicy.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>Parametry

*&*<br/>
Element do wyszukania.

### <a name="return-value"></a>Wartość zwracana

Zwraca indeks znalezionego elementu lub-1, jeśli nie można odnaleźć elementu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a> CSimpleArray:: GetData

Zwraca wskaźnik do danych przechowywanych w tablicy.

```
T* GetData() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do danych w tablicy.

## <a name="csimplearraygetsize"></a><a name="getsize"></a> CSimpleArray:: GetSize

Zwraca liczbę elementów przechowywanych w tablicy.

```
int GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę elementów przechowywanych w tablicy.

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a> CSimpleArray:: operator \[\]

Pobiera element z tablicy.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks elementu.

### <a name="return-value"></a>Wartość zwracana

Zwraca element tablicy, do której odwołuje się *nIndex*.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a> CSimpleArray:: operator =

Operator przypisania.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>Parametry

*src*<br/>
Tablica do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do zaktualizowanego `CSimpleArray` obiektu.

### <a name="remarks"></a>Uwagi

Kopiuje wszystkie elementy z `CSimpleArray` obiektu, do którego odwołuje się *src* , do bieżącego obiektu Array, zastępując wszystkie istniejące dane.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a> CSimpleArray:: Remove

Usuwa dany element z tablicy.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>Parametry

*&*<br/>
Element do usunięcia z tablicy.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli element zostanie znaleziony i usunięty, w przeciwnym razie ma wartość FALSE.

### <a name="remarks"></a>Uwagi

Po usunięciu elementu pozostałe elementy w tablicy są numerowane w celu wypełnienia pustego miejsca.

## <a name="csimplearrayremoveall"></a><a name="removeall"></a> CSimpleArray::

Usuwa wszystkie elementy z tablicy.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Uwagi

Usuwa wszystkie elementy, które są obecnie przechowywane w tablicy.

## <a name="csimplearrayremoveat"></a><a name="removeat"></a> CSimpleArray::RemoveAt

Usuwa określony element z tablicy.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks wskazujący element do usunięcia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli element został usunięty, FAŁSZ, jeśli indeks był nieprawidłowy.

### <a name="remarks"></a>Uwagi

Po usunięciu elementu pozostałe elementy w tablicy są numerowane w celu wypełnienia pustego miejsca.

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a> CSimpleArray:: Setatindex —

Ustaw określony element w tablicy.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks elementu, który ma zostać zmieniony.

*&*<br/>
Wartość do przypisania do określonego elementu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli wartość jest pomyślna, FAŁSZ, jeśli indeks jest nieprawidłowy.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
