---
description: 'Dowiedz się więcej na temat: Klasa CHeapPtr'
title: Klasa CHeapPtr
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: dc795c199562fa423a160b053c96983651d0812d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141651"
---
# <a name="cheapptr-class"></a>Klasa CHeapPtr

Klasa inteligentnego wskaźnika do zarządzania wskaźnikami sterty.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ obiektu, który ma być przechowywany na stercie.

*Alokator*<br/>
Klasa alokacji pamięci do użycia.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtr:: Allocate](#allocate)|Wywołaj tę metodę, aby przydzielić pamięć na stercie do przechowywania obiektów.|
|[CHeapPtr:: Reallocate](#reallocate)|Wywołaj tę metodę, aby ponownie przydzielić pamięć na stercie.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtr:: operator =](#operator_eq)|Operator przypisania.|

## <a name="remarks"></a>Uwagi

`CHeapPtr` pochodzi od [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) i domyślnie używa procedur CRT (w [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) do przydzielania i wolnej pamięci. Klasa [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) może służyć do konstruowania listy wskaźników sterty. Zobacz również [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), który używa procedur alokacji pamięci com.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcore. h

## <a name="cheapptrallocate"></a><a name="allocate"></a> CHeapPtr:: Allocate

Wywołaj tę metodę, aby przydzielić pamięć na stercie do przechowywania obiektów.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Parametry

*nElements*<br/>
Liczba elementów użytych do obliczenia ilości pamięci do przydzielenia. Wartość domyślna to 1.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli pamięć została pomyślnie przypisana, FAŁSZ w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Procedury alokatora służą do rezerwowania wystarczającej ilości pamięci na stercie do przechowywania obiektów *nElement* typu zdefiniowanego w konstruktorze.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a> CHeapPtr::CHeapPtr

Konstruktor.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Istniejący wskaźnik sterty lub `CHeapPtr` .

### <a name="remarks"></a>Uwagi

Można opcjonalnie utworzyć wskaźnik sterty przy użyciu istniejącego wskaźnika lub `CHeapPtr` obiektu. Jeśli tak, nowy `CHeapPtr` obiekt przyjmuje odpowiedzialność za zarządzanie nowym wskaźnikiem i zasobami.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a> CHeapPtr:: operator =

Operator przypisania.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Istniejący `CHeapPtr` obiekt.

### <a name="return-value"></a>Wartość zwracana

Zwraca odwołanie do zaktualizowanego elementu `CHeapPtr` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a> CHeapPtr:: Reallocate

Wywołaj tę metodę, aby ponownie przydzielić pamięć na stercie.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametry

*nElements*<br/>
Nowa liczba elementów użytych do obliczenia ilości pamięci do przydzielenia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli pamięć została pomyślnie przypisana, FAŁSZ w przypadku niepowodzenia.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>Zobacz także

[Klasa CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)<br/>
[Klasa CCRTAllocator](../../atl/reference/ccrtallocator-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
