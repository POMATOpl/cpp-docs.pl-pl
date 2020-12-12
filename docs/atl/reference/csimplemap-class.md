---
description: 'Dowiedz się więcej na temat: Klasa CSimpleMap'
title: Klasa CSimpleMap
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: 66640e3fcd325d59b82a10d98188a6fcd74ca79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140624"
---
# <a name="csimplemap-class"></a>Klasa CSimpleMap

Ta klasa zapewnia obsługę prostej tablicy mapowania.

## <a name="syntax"></a>Składnia

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>Parametry

*TKey*<br/>
Typ elementu klucza.

*TVal*<br/>
Typ elementu wartości.

*TEqual*<br/>
Obiekt cech, definiujący test równości dla elementów typu `T` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleMap:: _ArrayElementType](#_arrayelementtype)|Element typedef dla typu wartości.|
|[CSimpleMap:: _ArrayKeyType](#_arraykeytype)|Element typedef dla typu klucza.|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|Konstruktor.|
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleMap:: Add](#add)|Dodaje klucz i skojarzoną wartość do tablicy map.|
|[CSimpleMap:: FindKey —](#findkey)|Znajduje określony klucz.|
|[CSimpleMap::FindVal](#findval)|Znajduje konkretną wartość.|
|[CSimpleMap::GetKeyAt](#getkeyat)|Pobiera określony klucz.|
|[CSimpleMap:: GetSize](#getsize)|Zwraca liczbę wpisów w tablicy mapowania.|
|[CSimpleMap::GetValueAt](#getvalueat)|Pobiera określoną wartość.|
|[CSimpleMap:: Lookup](#lookup)|Zwraca wartość skojarzoną z danym kluczem.|
|[CSimpleMap:: Remove](#remove)|Usuwa klucz i pasującą wartość.|
|[CSimpleMap::](#removeall)|Usuwa wszystkie klucze i wartości.|
|[CSimpleMap::RemoveAt](#removeat)|Usuwa określony klucz i pasującą wartość.|
|[CSimpleMap::ReverseLookup](#reverselookup)|Zwraca klucz skojarzony z daną wartością.|
|[CSimpleMap::SetAt](#setat)|Ustawia wartość skojarzoną z danym kluczem.|
|[CSimpleMap:: Setatindex —](#setatindex)|Ustawia określony klucz i wartość.|

## <a name="remarks"></a>Uwagi

`CSimpleMap` zapewnia obsługę prostej tablicy mapowania dowolnego danego typu `T` , zarządzając nieuporządkowaną tablicą najważniejszych elementów i skojarzonych z nimi wartości.

Parametr `TEqual` zawiera sposób definiowania funkcji równości dla dwóch elementów typu `T` . Tworząc klasę podobną do [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), można zmienić zachowanie testu równości dla danej tablicy. Na przykład podczas pracy z tablicą wskaźników przydatne może być zdefiniowanie równości w zależności od wartości odniesienia wskaźników. Domyślna implementacja używa **operatora = = ()**.

Zarówno, `CSimpleMap` jak i [CSimpleArray](../../atl/reference/csimplearray-class.md) zapewniają zgodność z poprzednimi wersjami ATL, a pełniejsze i wydajne implementacje kolekcji są udostępniane przez [CAtlArray](../../atl/reference/catlarray-class.md) i [CAtlMap](../../atl/reference/catlmap-class.md).

W przeciwieństwie do innych kolekcji map w ATL i MFC, ta klasa jest implementowana przy użyciu prostej tablicy, a wyszukiwanie wyszukiwania wymaga wyszukiwania liniowego. `CAtlMap` należy używać, gdy tablica zawiera dużą liczbę elementów.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsimpcoll. h

## <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a> CSimpleMap:: Add

Dodaje klucz i skojarzoną wartość do tablicy map.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz.

*użyte*<br/>
Skojarzona wartość.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli klucz i wartość zostały pomyślnie dodane, w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Każda para klucz-wartość powoduje zwolnienie i ponowne przydzielenie pamięci z mapowaniem, aby zapewnić, że dane dla każdego z nich są zawsze przechowywane w sposób ciągły. Oznacza to, że drugi element klucza zawsze następuje bezpośrednio po pierwszym elemencie klucza w pamięci i tak dalej.

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a> CSimpleMap:: _ArrayElementType

Element typedef dla typu klucza.

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a> CSimpleMap:: _ArrayKeyType

Element typedef dla typu wartości.

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a> CSimpleMap::CSimpleMap

Konstruktor.

```
CSimpleMap();
```

### <a name="remarks"></a>Uwagi

Inicjuje składowe danych.

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a> CSimpleMap:: ~ CSimpleMap

Destruktor.

```
~CSimpleMap();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

## <a name="csimplemapfindkey"></a><a name="findkey"></a> CSimpleMap:: FindKey —

Znajduje określony klucz.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz, który ma zostać wyszukany.

### <a name="return-value"></a>Wartość zwracana

Zwraca indeks klucza, jeśli został znaleziony. w przeciwnym razie zwraca wartość-1.

## <a name="csimplemapfindval"></a><a name="findval"></a> CSimpleMap::FindVal

Znajduje konkretną wartość.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>Parametry

*użyte*<br/>
Wartość, dla której ma zostać wyszukane.

### <a name="return-value"></a>Wartość zwracana

Zwraca indeks wartości, jeśli zostanie odnaleziony; w przeciwnym razie zwraca wartość-1.

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a> CSimpleMap::GetKeyAt

Pobiera klucz o określonym indeksie.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks klucza do zwrócenia.

### <a name="return-value"></a>Wartość zwracana

Zwraca klucz przywoływany przez *nIndex*.

### <a name="remarks"></a>Uwagi

Indeks przesłany przez *nIndex* musi być prawidłowy, aby wartość zwracana była znacząca.

## <a name="csimplemapgetsize"></a><a name="getsize"></a> CSimpleMap:: GetSize

Zwraca liczbę wpisów w tablicy mapowania.

```
int GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę wpisów (klucz i wartość są jednym wpisem) w tablicy mapowania.

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a> CSimpleMap::GetValueAt

Pobiera wartość w określonym indeksie.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks wartości, która ma zostać zwrócona.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość przywoływaną przez *nIndex*.

### <a name="remarks"></a>Uwagi

Indeks przesłany przez *nIndex* musi być prawidłowy, aby wartość zwracana była znacząca.

## <a name="csimplemaplookup"></a><a name="lookup"></a> CSimpleMap:: Lookup

Zwraca wartość skojarzoną z danym kluczem.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz.

### <a name="return-value"></a>Wartość zwracana

Zwraca skojarzoną wartość. Jeśli nie zostanie znaleziony pasujący klucz, zwracana jest wartość NULL.

## <a name="csimplemapremove"></a><a name="remove"></a> CSimpleMap:: Remove

Usuwa klucz i pasującą wartość.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli klucz i zgodna wartość zostały pomyślnie usunięte, w przeciwnym razie FALSE.

## <a name="csimplemapremoveall"></a><a name="removeall"></a> CSimpleMap::

Usuwa wszystkie klucze i wartości.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Uwagi

Usuwa wszystkie klucze i wartości z obiektu tablicy mapowania.

## <a name="csimplemapremoveat"></a><a name="removeat"></a> CSimpleMap::RemoveAt

Usuwa klucz i skojarzoną wartość pod określonym indeksem.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks klucza i skojarzonej wartości do usunięcia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FAŁSZ, jeśli określony indeks jest nieprawidłowym indeksem.

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a> CSimpleMap::ReverseLookup

Zwraca klucz skojarzony z daną wartością.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>Parametry

*użyte*<br/>
Wartość.

### <a name="return-value"></a>Wartość zwracana

Zwraca skojarzony klucz. Jeśli nie zostanie znaleziony pasujący klucz, zwracana jest wartość NULL.

## <a name="csimplemapsetat"></a><a name="setat"></a> CSimpleMap::SetAt

Ustawia wartość skojarzoną z danym kluczem.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz.

*użyte*<br/>
Nowa wartość do przypisania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli klucz został znaleziony, a wartość została pomyślnie zmieniona, w przeciwnym razie FALSE.

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a> CSimpleMap:: Setatindex —

Ustawia klucz i wartość w określonym indeksie.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks, który odwołuje się do zmiany pary kluczy i wartości.

*głównych*<br/>
Nowy klucz.

*użyte*<br/>
Nowa wartość.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli wartość jest pomyślna, FAŁSZ, jeśli indeks jest nieprawidłowy.

### <a name="remarks"></a>Uwagi

Aktualizuje klucz i wartość wskazywane przez *nIndex*.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
