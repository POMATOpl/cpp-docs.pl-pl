---
description: Dowiedz się więcej o strukturze DispatchState
title: DispatchState — Struktura
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 1352a283d6f75d90872e75da92450a4867cf497f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169427"
---
# <a name="dispatchstate-structure"></a>DispatchState — Struktura

`DispatchState`Struktura służy do transferowania stanu do `IExecutionContext::Dispatch` metody. Opisano w nim sytuacje, w których `Dispatch` Metoda jest wywoływana w `IExecutionContext` interfejsie.

## <a name="syntax"></a>Składnia

```cpp
struct DispatchState;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[DispatchState::D ispatchState](#ctor)|Tworzy nowy `DispatchState` obiekt.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|Rozmiar tej struktury, który jest używany do przechowywania wersji.|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Wskazuje, czy ten kontekst wprowadza `Dispatch` metodę, ponieważ poprzedni kontekst został zablokowany asynchronicznie. Jest on używany tylko w kontekście planowania UMS i ma ustawioną wartość `0` dla wszystkich innych kontekstów wykonania.|
|[DispatchState:: m_reserved](#m_reserved)|Bity zarezerwowane do przekazywania przyszłych informacji.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`DispatchState`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a> DispatchState::D Konstruktor ispatchState

Tworzy nowy `DispatchState` obiekt.

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a> Element członkowski danych DispatchState:: m_dispatchStateSize

Rozmiar tej struktury, który jest używany do przechowywania wersji.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a> Element członkowski danych DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked

Wskazuje, czy ten kontekst wprowadza `Dispatch` metodę, ponieważ poprzedni kontekst został zablokowany asynchronicznie. Jest on używany tylko w kontekście planowania UMS i ma ustawioną wartość `0` dla wszystkich innych kontekstów wykonania.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a> Element członkowski danych DispatchState:: m_reserved

Bity zarezerwowane do przekazywania przyszłych informacji.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
