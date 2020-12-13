---
description: 'Dowiedz się więcej na temat: Klasa CCRTAllocator'
title: Klasa CCRTAllocator
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: 378a1c27a6c2dde9fbcb24eb9b51b64c3af7e8aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142067"
---
# <a name="ccrtallocator-class"></a>Klasa CCRTAllocator

Ta klasa udostępnia metody zarządzania pamięcią za pomocą procedur pamięci CRT.

## <a name="syntax"></a>Składnia

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCRTAllocator:: Allocate](#allocate)|Ruchom Wywołaj tę metodę, aby przydzielić pamięć.|
|[CCRTAllocator:: Free](#free)|Ruchom Wywołaj tę metodę, aby zwolnić pamięć.|
|[CCRTAllocator:: Reallocate](#reallocate)|Ruchom Wywołaj tę metodę, aby ponownie przydzielić pamięć.|

## <a name="remarks"></a>Uwagi

Ta klasa jest używana przez [CHeapPtr](../../atl/reference/cheapptr-class.md) do udostępniania procedur alokacji pamięci CRT. Odpowiednik klasy, [CComAllocator](../../atl/reference/ccomallocator-class.md), zapewnia te same metody przy użyciu procedur com.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcore. h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a> CCRTAllocator:: Allocate

Wywołaj tę funkcję statyczną w celu przydzielenia pamięci.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametry

*nBytes*<br/>
Liczba bajtów do przydzielenia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik void do przydzieloną miejsce lub wartość NULL, jeśli jest za mało dostępnej pamięci.

### <a name="remarks"></a>Uwagi

Przydziela pamięć. Aby uzyskać więcej informacji, zobacz [malloc](../../c-runtime-library/reference/malloc.md) .

## <a name="ccrtallocatorfree"></a><a name="free"></a> CCRTAllocator:: Free

Wywołaj tę funkcję statyczną, aby zwolnić pamięć.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Wskaźnik do przydzieloną pamięć.

### <a name="remarks"></a>Uwagi

Zwalnia przydzieloną pamięć. Aby uzyskać więcej informacji, zobacz [bezpłatnie](../../c-runtime-library/reference/free.md) .

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a> CCRTAllocator:: Reallocate

Wywołaj tę funkcję statyczną, aby ponownie przydzielić pamięć.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametry

*St*<br/>
Wskaźnik do przydzieloną pamięć.

*nBytes*<br/>
Liczba bajtów do ponownego przydzielenia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik void do przydzieloną miejsce lub wartość NULL, jeśli jest za mało pamięci.

### <a name="remarks"></a>Uwagi

Zmienia rozmiar przydzieloną pamięci. Aby uzyskać więcej informacji, zobacz temat [realloc](../../c-runtime-library/reference/realloc.md) .

## <a name="see-also"></a>Zobacz też

[Klasa CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Klasa CComAllocator](../../atl/reference/ccomallocator-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
