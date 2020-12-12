---
description: Dowiedz się więcej o strukturze MutexTraits
title: MutexTraits — Struktura
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: e3dfcee1251794734ed5cf787096361403d80c7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330819"
---
# <a name="mutextraits-structure"></a>MutexTraits — Struktura

Definiuje typowe cechy klasy [mutex](mutex-class.md) .

## <a name="syntax"></a>Składnia

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

Nazwa                           | Opis
------------------------------ | ------------------------------------------------
[MutexTraits:: Unlock](#unlock) | Zwalnia kontrolę wykluczającą zasobu udostępnionego.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki:: HandleTraits

## <a name="mutextraitsunlock-method"></a><a name="unlock"></a> MutexTraits:: Unlock — Metoda

Zwalnia kontrolę wykluczającą zasobu udostępnionego.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Dojście do obiektu mutex.
