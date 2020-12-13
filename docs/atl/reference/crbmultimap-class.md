---
description: 'Dowiedz się więcej na temat: Klasa CRBMultiMap'
title: Klasa CRBMultiMap
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: 8dfe644521cb7ec4135c5c1f71d36371ac1706ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141027"
---
# <a name="crbmultimap-class"></a>Klasa CRBMultiMap

Ta klasa reprezentuje strukturę mapowania, która pozwala na każdy klucz można skojarzyć z więcej niż jedną wartością przy użyciu Red-Black drzewie binarnym.

## <a name="syntax"></a>Składnia

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>Parametry

*K*<br/>
Typ elementu klucza.

*V*<br/>
Typ elementu wartości.

*KTraits*<br/>
Kod używany do kopiowania lub przenoszenia elementów klucza. Aby uzyskać więcej informacji, zobacz [Klasa CElementTraits](../../atl/reference/celementtraits-class.md) .

*VTraits*<br/>
Kod używany do kopiowania lub przenoszenia elementów wartości.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Konstruktor.|
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Wywołaj tę metodę, aby znaleźć pozycję pierwszego elementu z danym kluczem.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Wywołaj tę metodę, aby uzyskać wartość skojarzoną z danym kluczem i zaktualizować wartość pozycji.|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Wywołaj tę metodę, aby uzyskać element skojarzony z danym kluczem i zaktualizować wartość pozycji.|
|[CRBMultiMap:: INSERT](#insert)|Wywołaj tę metodę, aby wstawić parę elementów do mapy.|
|[CRBMultiMap::RemoveKey](#removekey)|Wywołaj tę metodę, aby usunąć wszystkie elementy klucza/wartości dla danego klucza.|

## <a name="remarks"></a>Uwagi

`CRBMultiMap` zapewnia obsługę tablicy mapowania dowolnego danego typu, zarządzającą uporządkowaną tablicą elementów i wartości klucza. W przeciwieństwie do klasy [CRBMap](../../atl/reference/crbmap-class.md) każdy klucz może być skojarzony z więcej niż jedną wartością.

Elementy (składające się z klucza i wartości) są przechowywane w strukturze drzewa binarnego przy użyciu metody [CRBMultiMap:: INSERT](#insert) . Elementy można usunąć za pomocą metody [CRBMultiMap:: RemoveKey](#removekey) , która usuwa wszystkie elementy, które pasują do danego klucza.

Przechodzenie drzewa jest możliwe przy użyciu metod takich jak [CRBTree:: GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree:: GetNext](../../atl/reference/crbtree-class.md#getnext)i [CRBTree:: GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Dostęp do potencjalnie wielu wartości na klucz jest możliwy przy użyciu metod [CRBMultiMap:: FindFirstWithKey](#findfirstwithkey), [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)i [CRBMultiMap:: GetNextWithKey](#getnextwithkey) . Zobacz przykład dla [CRBMultiMap:: CRBMultiMap](#crbmultimap) , aby poznać ilustrację w tym temacie.

Parametry *KTraits* i *VTraits* są klasami cech, które zawierają dowolny dodatkowy kod wymagany do kopiowania lub przenoszenia elementów.

`CRBMultiMap` pochodzi od [CRBTree](../../atl/reference/crbtree-class.md), który implementuje drzewo binarne przy użyciu algorytmu Red-Black. Alternatywa dla `CRBMultiMap` i `CRBMap` jest oferowana przez klasę [CAtlMap](../../atl/reference/catlmap-class.md) . Jeśli trzeba przechowywać tylko niewielką liczbę elementów, należy rozważyć użycie klasy [CSimpleMap](../../atl/reference/csimplemap-class.md) .

Dokładniejsze Omówienie różnych klas kolekcji i ich funkcji oraz charakterystyki wydajności znajdują się w temacie [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a> CRBMultiMap::CRBMultiMap

Konstruktor.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametry

*nBlockSize*<br/>
Rozmiar bloku.

### <a name="remarks"></a>Uwagi

*NBlockSize* parametr jest miarą ilości pamięci przydzieloną, gdy wymagany jest nowy element. Większe rozmiary bloków redukują wywołania procedur alokacji pamięci, ale wykorzystują więcej zasobów. Domyślnie przydzieli miejsce na 10 elementów jednocześnie.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a> CRBMultiMap:: ~ CRBMultiMap

Destruktor.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a> CRBMultiMap::FindFirstWithKey

Wywołaj tę metodę, aby znaleźć pozycję pierwszego elementu z danym kluczem.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa klucz, który identyfikuje element, który ma zostać znaleziony.

### <a name="return-value"></a>Wartość zwracana

Zwraca pozycję pierwszego elementu klucza/wartości, jeśli klucz zostanie znaleziony, w przeciwnym razie ma wartość NULL.

### <a name="remarks"></a>Uwagi

Klucz w `CRBMultiMap` może mieć co najmniej jedną skojarzoną wartość. Ta metoda zapewnia wartość pozycji pierwszej wartości (która może być w rzeczywistości jedyną wartością) skojarzoną z tym konkretnym kluczem. Zwracana wartość pozycji może być następnie używana z [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey) lub [CRBMultiMap:: GetNextWithKey](#getnextwithkey) , aby uzyskać wartość i zaktualizować pozycję.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

Zobacz przykład dla [CRBMultiMap:: CRBMultiMap](#crbmultimap).

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a> CRBMultiMap::GetNextValueWithKey

Wywołaj tę metodę, aby uzyskać wartość skojarzoną z danym kluczem i zaktualizować wartość pozycji.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametry

*Terminal*<br/>
Wartość pozycji uzyskana przy użyciu wywołania metody [CRBMultiMap:: FindFirstWithKey](#findfirstwithkey) lub [CRBMultiMap:: GetNextWithKey](#getnextwithkey)lub poprzedniego wywołania metody `GetNextValueWithKey` .

*głównych*<br/>
Określa klucz, który identyfikuje element, który ma zostać znaleziony.

### <a name="return-value"></a>Wartość zwracana

Zwraca parę elementów skojarzoną z danym kluczem.

### <a name="remarks"></a>Uwagi

Wartość pozycji jest aktualizowana w celu wskazywania następnej wartości skojarzonej z kluczem. Jeśli nie ma więcej wartości, wartość pozycji jest ustawiona na wartość NULL.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

Zobacz przykład dla [CRBMultiMap:: CRBMultiMap](#crbmultimap).

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a> CRBMultiMap::GetNextWithKey

Wywołaj tę metodę, aby uzyskać element skojarzony z danym kluczem i zaktualizować wartość pozycji.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametry

*Terminal*<br/>
Wartość pozycji uzyskana przy użyciu wywołania metody [CRBMultiMap:: FindFirstWithKey](#findfirstwithkey) lub [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)lub poprzedniego wywołania metody `GetNextWithKey` .

*głównych*<br/>
Określa klucz, który identyfikuje element, który ma zostać znaleziony.

### <a name="return-value"></a>Wartość zwracana

Zwraca następny element [klasy CRBTree:: CPair](crbtree-class.md#cpair_class) skojarzony z danym kluczem.

### <a name="remarks"></a>Uwagi

Wartość pozycji jest aktualizowana w celu wskazywania następnej wartości skojarzonej z kluczem. Jeśli nie ma więcej wartości, wartość pozycji jest ustawiona na wartość NULL.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

## <a name="crbmultimapinsert"></a><a name="insert"></a> CRBMultiMap:: INSERT

Wywołaj tę metodę, aby wstawić parę elementów do mapy.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do dodania do `CRBMultiMap` obiektu.

*wartość*<br/>
Wartość, która ma zostać dodana do `CRBMultiMap` obiektu, skojarzona z *kluczem*.

### <a name="return-value"></a>Wartość zwracana

Zwraca pozycję pary klucz/wartość w `CRBMultiMap` obiekcie.

### <a name="remarks"></a>Uwagi

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

Zobacz przykład dla [CRBMultiMap:: CRBMultiMap](#crbmultimap).

## <a name="crbmultimapremovekey"></a><a name="removekey"></a> CRBMultiMap::RemoveKey

Wywołaj tę metodę, aby usunąć wszystkie elementy klucza/wartości dla danego klucza.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa klucz identyfikujący elementy, które mają zostać usunięte.

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę wartości skojarzonych z danym kluczem.

### <a name="remarks"></a>Uwagi

`RemoveKey` usuwa wszystkie elementy klucza/wartości, które mają klucz pasujący do *klucza*.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

Zobacz przykład dla [CRBMultiMap:: CRBMultiMap](#crbmultimap).

## <a name="see-also"></a>Zobacz też

[Klasa CRBTree](../../atl/reference/crbtree-class.md)<br/>
[Klasa CAtlMap](../../atl/reference/catlmap-class.md)<br/>
[Klasa CRBMap](../../atl/reference/crbmap-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
