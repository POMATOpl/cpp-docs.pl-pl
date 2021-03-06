---
description: Dowiedz się więcej o strukturze ITopologyNode
title: ITopologyNode — Struktura
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 1d603e35728791ff94e43b03d890061dec834660
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334361"
---
# <a name="itopologynode-structure"></a>ITopologyNode — Struktura

Interfejs do węzła topologii zdefiniowany przez Menedżer zasobów. Węzeł zawiera jeden lub więcej zasobów wykonawczych.

## <a name="syntax"></a>Składnia

```cpp
struct ITopologyNode;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ITopologyNode:: GetExecutionResourceCount —](#getexecutionresourcecount)|Zwraca liczbę zasobów wykonywania zgrupowanych razem w tym węźle.|
|[ITopologyNode:: GetFirstExecutionResource —](#getfirstexecutionresource)|Zwraca pierwszy zasób wykonania zgrupowany w tym węźle w kolejności wyliczania.|
|[ITopologyNode:: GetId —](#getid)|Zwraca unikatowy identyfikator Menedżer zasobów dla tego węzła.|
|[ITopologyNode:: GetNext](#getnext)|Zwraca interfejs do następnego węzła topologii w kolejności wyliczania.|
|[ITopologyNode:: GetNumaNode](#getnumanode)|Zwraca numer węzła NUMA przypisanego do systemu Windows, do którego należy ten węzeł Menedżera zasobów.|

## <a name="remarks"></a>Uwagi

Ten interfejs jest zazwyczaj używany do przeszukiwania topologii systemu widzianych przez Menedżer zasobów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ITopologyNode`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a> ITopologyNode:: GetExecutionResourceCount —, Metoda

Zwraca liczbę zasobów wykonywania zgrupowanych razem w tym węźle.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Liczba zasobów wykonywania zgrupowanych ze sobą w tym węźle.

## <a name="itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a> ITopologyNode:: GetFirstExecutionResource —, Metoda

Zwraca pierwszy zasób wykonania zgrupowany w tym węźle w kolejności wyliczania.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Pierwszy zasób wykonywania zgrupowany w tym węźle w kolejności wyliczania.

## <a name="itopologynodegetid-method"></a><a name="getid"></a> ITopologyNode:: GetId —, Metoda

Zwraca unikatowy identyfikator Menedżer zasobów dla tego węzła.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Unikatowy identyfikator Menedżer zasobów dla tego węzła.

### <a name="remarks"></a>Uwagi

Środowisko uruchomieniowe współbieżności reprezentuje wątki sprzętowe w systemie w grupach węzłów procesora. Węzły są zwykle wyprowadzane z topologii sprzętowej systemu. Na przykład wszystkie procesory w określonym gnieździe lub określony węzeł NUMA mogą należeć do tego samego węzła procesora. Menedżer zasobów przypisuje unikatowe identyfikatory do tych węzłów, rozpoczynając od `0` do i włącznie `nodeCount - 1` , gdzie `nodeCount` reprezentuje łączną liczbę węzłów procesora w systemie.

Liczbę węzłów można uzyskać z funkcji [GetProcessorNodeCount —](concurrency-namespace-functions.md).

## <a name="itopologynodegetnext-method"></a><a name="getnext"></a> ITopologyNode:: GetNext — Metoda

Zwraca interfejs do następnego węzła topologii w kolejności wyliczania.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Interfejs do następnego węzła w kolejności wyliczania. Jeśli w kolejności wyliczania topologii systemu nie ma więcej węzłów, ta metoda zwróci wartość `NULL` .

## <a name="itopologynodegetnumanode-method"></a><a name="getnumanode"></a> ITopologyNode:: GetNumaNode, Metoda

Zwraca numer węzła NUMA przypisanego do systemu Windows, do którego należy ten węzeł Menedżera zasobów.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Numer węzła NUMA przypisany do systemu Windows, do którego należy ten węzeł Menedżer zasobów.

### <a name="remarks"></a>Uwagi

Serwer proxy wątku uruchomiony w wirtualnym katalogu głównym procesora należącym do tego węzła będzie miał koligację do co najmniej poziomu węzła NUMA dla węzła NUMA zwróconego przez tę metodę.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
