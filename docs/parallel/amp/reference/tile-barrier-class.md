---
description: Dowiedz się więcej na temat klasy tile_barrier
title: tile_barrier — Klasa
ms.date: 03/27/2019
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
ms.openlocfilehash: b4fd1758f9786f4cbb78556daadb0801795ca9c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321711"
---
# <a name="tile_barrier-class"></a>tile_barrier — Klasa

Synchronizuje wykonywanie wątków, które są uruchomione w grupie wątków (kafelku) przy użyciu `wait` metod. Tylko środowisko uruchomieniowe może utworzyć wystąpienie tej klasy.

## <a name="syntax"></a>Składnia

```cpp
class tile_barrier;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor tile_barrier](#ctor)|Inicjuje nowe wystąpienie klasy `tile_barrier`.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[trwa](#wait)|Instruuje wszystkie wątki w grupie wątków (kafelek), aby zatrzymać wykonywanie do momentu zakończenia wszystkich wątków na kafelku.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Blokuje wykonywanie wszystkich wątków we fragmencie do momentu zakończenia wszystkich operacji dostępu do pamięci, a wszystkie wątki we fragmencie osiągną to wywołanie.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Blokuje wykonywanie wszystkich wątków we fragmencie do momentu zakończenia wszystkich operacji dostępu do pamięci globalnej, a wszystkie wątki we fragmencie osiągną to wywołanie.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Blokuje wykonywanie wszystkich wątków we fragmencie do momentu zakończenia wszystkich `tile_static` operacji dostępu do pamięci, a wszystkie wątki we fragmencie osiągną to wywołanie.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`tile_barrier`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp. h

**Przestrzeń nazw:** Współbieżności

## <a name="tile_barrier-constructor"></a><a name="ctor"></a> Konstruktor tile_barrier

Inicjuje nowe wystąpienie klasy przez skopiowanie istniejącej.

### <a name="syntax"></a>Składnia

```cpp
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
`tile_barrier`Obiekt do skopiowania.

## <a name="wait"></a>czas oczekiwania

Instruuje wszystkie wątki w grupie wątków (kafelek), aby zatrzymać wykonywanie do momentu zakończenia wszystkich wątków na kafelku.

### <a name="syntax"></a>Składnia

```cpp
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a><a name="wait_with_all_memory_fence"></a> wait_with_all_memory_fence

Blokuje wykonywanie wszystkich wątków we fragmencie, dopóki wszystkie wątki we fragmencie osiągną to wywołanie. Daje to pewność, że wszystkie dostępy do pamięci są widoczne dla innych wątków w kafelku wątku i zostały wykonane w kolejności programu.

### <a name="syntax"></a>Składnia

```cpp
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="a-namewait_with_global_memory_fence-wait_with_global_memory_fence"></a><a name="wait_with_global_memory_fence"> wait_with_global_memory_fence

Blokuje wykonywanie wszystkich wątków we fragmencie, dopóki wszystkie wątki we fragmencie osiągną to wywołanie. Gwarantuje to, że wszystkie dostępy do pamięci globalnej są widoczne dla innych wątków w kafelku wątku i zostały wykonane w kolejności programu.

### <a name="syntax"></a>Składnia

```cpp
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="a-namewait_with_tile_static_memory_fence-wait_with_tile_static_memory_fence"></a><a name="wait_with_tile_static_memory_fence"> wait_with_tile_static_memory_fence

Blokuje wykonywanie wszystkich wątków we fragmencie, dopóki wszystkie wątki we fragmencie osiągną to wywołanie. Daje to pewność, że `tile_static` dostęp do pamięci będzie widoczny dla innych wątków w kafelku wątku i zostały wykonane w kolejności programu.

### <a name="syntax"></a>Składnia

```cpp
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
