---
description: 'Dowiedz się więcej na temat: Klasa CRBMap'
title: Klasa CRBMap
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: 55d96bfd2c7b043bdbdc4c1ee1f329c9b77b9ca9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141053"
---
# <a name="crbmap-class"></a>Klasa CRBMap

Ta klasa reprezentuje strukturę mapowania przy użyciu Red-Black drzewie binarnym.

## <a name="syntax"></a>Składnia

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMap::CRBMap](#crbmap)|Konstruktor.|
|[CRBMap:: ~ CRBMap](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRBMap:: Lookup](#lookup)|Wywołaj tę metodę, aby wyszukiwać klucze lub wartości w `CRBMap` obiekcie.|
|[CRBMap::RemoveKey](#removekey)|Wywołaj tę metodę, aby usunąć element z `CRBMap` obiektu, uwzględniając klucz.|
|[CRBMap::SetAt](#setat)|Wywołaj tę metodę, aby wstawić parę elementów do mapy.|

## <a name="remarks"></a>Uwagi

`CRBMap` zapewnia obsługę tablicy mapowania dowolnego danego typu, zarządzającą uporządkowaną tablicą elementów i skojarzonych z nimi wartości. Każdy klucz może mieć tylko jedną skojarzoną wartość. Elementy (składające się z klucza i wartości) są przechowywane w strukturze drzewa binarnego przy użyciu metody [CRBMap:: SetAt](#setat) . Elementy można usunąć za pomocą metody [CRBMap:: RemoveKey](#removekey) , która usuwa element z daną wartością klucza.

Przechodzenie drzewa jest możliwe przy użyciu metod takich jak [CRBTree:: GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree:: GetNext](../../atl/reference/crbtree-class.md#getnext)i [CRBTree:: GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).

Parametry *KTraits* i *VTraits* są klasami cech, które zawierają dowolny dodatkowy kod wymagany do kopiowania lub przenoszenia elementów.

`CRBMap` pochodzi od [CRBTree](../../atl/reference/crbtree-class.md), który implementuje drzewo binarne przy użyciu algorytmu Red-Black. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) to odmiana umożliwiająca wiele wartości dla każdego klucza. Jest on zbyt pochodny `CRBTree` , a więc udostępnia wiele funkcji w programie `CRBMap` .

Alternatywa dla obu `CRBMap` i `CRBMultiMap` jest oferowana przez klasę [CAtlMap](../../atl/reference/catlmap-class.md) . Jeśli trzeba przechowywać tylko niewielką liczbę elementów, należy rozważyć użycie klasy [CSimpleMap](../../atl/reference/csimplemap-class.md) .

Dokładniejsze Omówienie różnych klas kolekcji i ich funkcji oraz charakterystyki wydajności znajdują się w temacie [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a> CRBMap::CRBMap

Konstruktor.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametry

*nBlockSize*<br/>
Rozmiar bloku.

### <a name="remarks"></a>Uwagi

*NBlockSize* parametr jest miarą ilości pamięci przydzieloną, gdy wymagany jest nowy element. Większe rozmiary bloków redukują wywołania procedur alokacji pamięci, ale wykorzystują więcej zasobów. Domyślnie przydzieli miejsce na 10 elementów jednocześnie.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a> CRBMap:: ~ CRBMap

Destruktor.

```
~CRBMap() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

## <a name="crbmaplookup"></a><a name="lookup"></a> CRBMap:: Lookup

Wywołaj tę metodę, aby wyszukiwać klucze lub wartości w `CRBMap` obiekcie.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa klucz, który identyfikuje element, który ma zostać wyszukany.

*wartość*<br/>
Zmienna, która otrzymuje wartość wyszukiwania.

### <a name="return-value"></a>Wartość zwracana

Pierwsza forma metody zwraca wartość true, jeśli klucz zostanie znaleziony, w przeciwnym razie false. Drugi i trzeci formularz zwracają wskaźnik do [CPair](crbtree-class.md#cpair_class).

### <a name="remarks"></a>Uwagi

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a> CRBMap::RemoveKey

Wywołaj tę metodę, aby usunąć element z `CRBMap` obiektu, uwzględniając klucz.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz odpowiadający parze elementu, który chcesz usunąć.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli klucz zostanie znaleziony i usunięty, wartość false w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a> CRBMap::SetAt

Wywołaj tę metodę, aby wstawić parę elementów do mapy.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do dodania do `CRBMap` obiektu.

*wartość*<br/>
Wartość, która ma zostać dodana do `CRBMap` obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca pozycję pary klucz/wartość w `CRBMap` obiekcie.

### <a name="remarks"></a>Uwagi

`SetAt` Zastępuje istniejący element, jeśli zostanie znaleziony pasujący klucz. Jeśli klucz nie zostanie znaleziony, zostanie utworzona nowa para klucz/wartość.

Zapoznaj się z dokumentacją klasy bazowej [CRBTree](../../atl/reference/crbtree-class.md) , aby uzyskać informacje na temat innych dostępnych metod.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>Zobacz także

[Klasa CRBTree](../../atl/reference/crbtree-class.md)<br/>
[Klasa CAtlMap](../../atl/reference/catlmap-class.md)<br/>
[Klasa CRBMultiMap](../../atl/reference/crbmultimap-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
