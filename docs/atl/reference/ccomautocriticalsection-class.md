---
description: 'Dowiedz się więcej na temat: Klasa CComAutoCriticalSection'
title: Klasa CComAutoCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 2441c714b95a3bbefed4a699055d14c6915cffda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146968"
---
# <a name="ccomautocriticalsection-class"></a>Klasa CComAutoCriticalSection

`CComAutoCriticalSection` zapewnia metody uzyskiwania i zwalniania własności obiektu sekcji krytycznej.

## <a name="syntax"></a>Składnia

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Konstruktor.|
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Destruktor.|

## <a name="remarks"></a>Uwagi

`CComAutoCriticalSection` jest podobna do klasy [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), z wyjątkiem, że `CComAutoCriticalSection` automatycznie inicjuje obiekt sekcji krytycznej w konstruktorze.

Zwykle używasz `CComAutoCriticalSection` **`typedef`** nazwy [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Ta nazwa odwołuje `CComAutoCriticalSection` się, gdy jest używana [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) .

`Init`Metody i `Term` z [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) nie są dostępne podczas korzystania z tej klasy.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcore. h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a> CComAutoCriticalSection::CComAutoCriticalSection

Konstruktor.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Uwagi

Wywołuje funkcję Win32 [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), która inicjuje obiekt sekcji krytycznej.

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a> CComAutoCriticalSection:: ~ CComAutoCriticalSection

Destruktor.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Uwagi

Destruktor wywołuje [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection), który zwalnia wszystkie zasoby systemowe używane przez obiekt sekcji krytycznej.

## <a name="see-also"></a>Zobacz też

[Klasa CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasa CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)
