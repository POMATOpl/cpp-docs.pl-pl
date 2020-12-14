---
description: Dowiedz się więcej o strukturze HANDLENullTraits
title: HANDLENullTraits — Struktura
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: 14d5eaab36be24b5450b66c35c9cf5cbba39ea4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229252"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits — Struktura

Definiuje typowe cechy niezainicjowanego dojścia.

## <a name="syntax"></a>Składnia

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa   | Opis
------ | ---------------------
`Type` | Synonim dla UCHWYTu.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                  | Opis
----------------------------------------------------- | -----------------------------
[HANDLENullTraits:: Close](#close)                     | Zamyka określone dojście.
[HANDLENullTraits:: GetInvalidValue —](#getinvalidvalue) | Reprezentuje nieprawidłowe dojście.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`HANDLENullTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki:: HandleTraits

## <a name="handlenulltraitsclose"></a><a name="close"></a> HANDLENullTraits:: Close

Zamyka określone dojście.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Uchwyt do zamknięcia.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli dojście *h* zostało zamknięte pomyślnie; w przeciwnym razie **`false`** .

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> HANDLENullTraits:: GetInvalidValue —

Reprezentuje nieprawidłowe dojście.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca **`nullptr`** .
