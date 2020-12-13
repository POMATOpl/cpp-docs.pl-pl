---
description: 'Dowiedz się więcej na temat: Klasa CCRTHeap'
title: Klasa CCRTHeap
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: c256139f37a4b0caa0a60f1a87fd71b6a3a8de3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142015"
---
# <a name="ccrtheap-class"></a>Klasa CCRTHeap

Ta klasa implementuje [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) przy użyciu funkcji sterty CRT.

## <a name="syntax"></a>Składnia

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCRTHeap:: Allocate](#allocate)|Wywołaj tę metodę, aby przydzielić blok pamięci.|
|[CCRTHeap:: Free](#free)|Wywołaj tę metodę, aby zwolnić blok pamięci przydzielonej przez ten Menedżer pamięci.|
|[CCRTHeap:: GetSize](#getsize)|Wywołaj tę metodę, aby uzyskać przydzielonego rozmiaru bloku pamięci przydzielonego przez ten Menedżer pamięci.|
|[CCRTHeap:: Reallocate](#reallocate)|Wywołaj tę metodę, aby ponownie przydzielić pamięć przydzieloną przez ten Menedżer pamięci.|

## <a name="remarks"></a>Uwagi

`CCRTHeap` implementuje funkcje alokacji pamięci przy użyciu funkcji sterty CRT, w tym [malloc](../../c-runtime-library/reference/malloc.md), [Free](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md)i [_msize](../../c-runtime-library/reference/msize.md).

## <a name="example"></a>Przykład

Zobacz przykład dla [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlmem. h

## <a name="ccrtheapallocate"></a><a name="allocate"></a> CCRTHeap:: Allocate

Wywołaj tę metodę, aby przydzielić blok pamięci.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametry

*nBytes*<br/>
Żądana liczba bajtów w nowym bloku pamięci.

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do początku nowo przydzielony blok pamięci.

### <a name="remarks"></a>Uwagi

Wywołanie [CCRTHeap:: Free](#free) lub [CCRTHeap:: Reallocate](#reallocate) w celu zwolnienia pamięci przydzielonej przez tę metodę.

Zaimplementowane przy użyciu opcji [malloc](../../c-runtime-library/reference/malloc.md).

## <a name="ccrtheapfree"></a><a name="free"></a> CCRTHeap:: Free

Wywołaj tę metodę, aby zwolnić blok pamięci przydzielonej przez ten Menedżer pamięci.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Wskaźnik do pamięci przydzielonej wcześniej przez ten Menedżer pamięci. Wartość NULL jest prawidłowa i nic nie robi.

### <a name="remarks"></a>Uwagi

Zaimplementowany przy użyciu opcji [Free](../../c-runtime-library/reference/free.md).

## <a name="ccrtheapgetsize"></a><a name="getsize"></a> CCRTHeap:: GetSize

Wywołaj tę metodę, aby uzyskać przydzielonego rozmiaru bloku pamięci przydzielonego przez ten Menedżer pamięci.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Wskaźnik do pamięci przydzielonej wcześniej przez ten Menedżer pamięci.

### <a name="return-value"></a>Wartość zwracana

Zwraca rozmiar przydzielony blok pamięci w bajtach.

### <a name="remarks"></a>Uwagi

Zaimplementowane przy użyciu [_msize](../../c-runtime-library/reference/msize.md).

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a> CCRTHeap:: Reallocate

Wywołaj tę metodę, aby ponownie przydzielić pamięć przydzieloną przez ten Menedżer pamięci.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Wskaźnik do pamięci przydzielonej wcześniej przez ten Menedżer pamięci.

*nBytes*<br/>
Żądana liczba bajtów w nowym bloku pamięci.

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do początku nowo przydzielony blok pamięci.

### <a name="remarks"></a>Uwagi

Wywołaj [CCRTHeap:: Free](#free) , aby zwolnić pamięć przydzieloną przez tę metodę. Zaimplementowane przy użyciu funkcji [realloc](../../c-runtime-library/reference/realloc.md).

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasa CComHeap](../../atl/reference/ccomheap-class.md)<br/>
[Klasa CWin32Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Klasa CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Klasa CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Klasa IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
