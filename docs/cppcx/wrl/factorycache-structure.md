---
description: Dowiedz się więcej o strukturze FactoryCache
title: FactoryCache — Struktura
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 3e9ee084a063eb8094c309dee412a8793801921b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198557"
---
# <a name="factorycache-structure"></a>FactoryCache — Struktura

Obsługuje infrastrukturę biblioteki szablonów w języku C++ środowisko wykonawcze systemu Windows i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Uwagi

Zawiera lokalizację fabryki klasy i wartość, która identyfikuje zarejestrowany obiekt klasy WRT lub COM.

## <a name="members"></a>Elementy członkowskie

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

Nazwa                              | Opis
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache:: cookie](#cookie)   | Zawiera wartość, która identyfikuje zarejestrowany środowisko wykonawcze systemu Windows lub obiekt klasy COM, i jest później używany do wyrejestrowania obiektu.
[FactoryCache:: Factory](#factory) | Wskazuje środowisko wykonawcze systemu Windows lub fabrykę klas COM.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`FactoryCache`

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="factorycachecookie"></a><a name="cookie"></a> FactoryCache:: cookie

Obsługuje infrastrukturę biblioteki szablonów w języku C++ środowisko wykonawcze systemu Windows i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Uwagi

Zawiera wartość, która identyfikuje zarejestrowany środowisko wykonawcze systemu Windows lub obiekt klasy COM, i jest później używany do wyrejestrowania obiektu.

## <a name="factorycachefactory"></a><a name="factory"></a> FactoryCache:: Factory

Obsługuje infrastrukturę biblioteki szablonów w języku C++ środowisko wykonawcze systemu Windows i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Uwagi

Wskazuje środowisko wykonawcze systemu Windows lub fabrykę klas COM.
