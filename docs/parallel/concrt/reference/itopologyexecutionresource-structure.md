---
description: Dowiedz się więcej o strukturze ITopologyExecutionResource
title: ITopologyExecutionResource — Struktura
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: c2567cf9e34e0b27308e331056d5e0dbc99b2779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334381"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource — Struktura

Interfejs do zasobu wykonywania określony przez Menedżer zasobów.

## <a name="syntax"></a>Składnia

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ITopologyExecutionResource:: GetId —](#getid)|Zwraca unikatowy identyfikator Menedżer zasobów dla tego zasobu wykonania.|
|[ITopologyExecutionResource:: GetNext](#getnext)|Zwraca interfejs do następnego zasobu wykonania w kolejności wyliczania.|

## <a name="remarks"></a>Uwagi

Ten interfejs jest zazwyczaj używany do przeszukiwania topologii systemu widzianych przez Menedżer zasobów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ITopologyExecutionResource`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a> ITopologyExecutionResource:: GetId —, Metoda

Zwraca unikatowy identyfikator Menedżer zasobów dla tego zasobu wykonania.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Unikatowy identyfikator Menedżer zasobów dla tego zasobu wykonania.

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a> ITopologyExecutionResource:: GetNext — Metoda

Zwraca interfejs do następnego zasobu wykonania w kolejności wyliczania.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Interfejs do następnego zasobu wykonywania w kolejności wyliczania. Jeśli nie ma więcej węzłów w kolejności wyliczania węzła, do którego należy ten zasób wykonania, ta metoda zwróci wartość `NULL` .

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
