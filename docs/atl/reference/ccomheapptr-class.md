---
description: 'Dowiedz się więcej na temat: Klasa CComHeapPtr'
title: Klasa CComHeapPtr
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 18865923e86a2392260ab1e6dedde2f37b9b4ea3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146630"
---
# <a name="ccomheapptr-class"></a>Klasa CComHeapPtr

Klasa inteligentnego wskaźnika do zarządzania wskaźnikami sterty.

## <a name="syntax"></a>Składnia

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ obiektu, który ma być przechowywany na stercie.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Konstruktor.|

## <a name="remarks"></a>Uwagi

`CComHeapPtr` pochodzi z `CHeapPtr` , ale używa [CComAllocator](../../atl/reference/ccomallocator-class.md) do przydzielania pamięci za pomocą procedur com. Zobacz [CHeapPtr](../../atl/reference/cheapptr-class.md) i [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) dla dostępnych metod.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a> CComHeapPtr::CComHeapPtr

Konstruktor.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>Parametry

*pData*<br/>
Istniejący `CComHeapPtr` obiekt.

### <a name="remarks"></a>Uwagi

Można opcjonalnie utworzyć wskaźnik sterty przy użyciu istniejącego `CComHeapPtr` obiektu. Jeśli tak, nowy `CComHeapPtr` obiekt przyjmuje odpowiedzialność za zarządzanie nowym wskaźnikiem i zasobami.

## <a name="see-also"></a>Zobacz też

[Klasa CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Klasa CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)<br/>
[Klasa CComAllocator](../../atl/reference/ccomallocator-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
