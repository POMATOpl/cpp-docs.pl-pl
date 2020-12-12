---
description: Dowiedz się więcej o strukturze CreatorMap
title: CreatorMap — Struktura
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 0ef3b441390a22a6c4b35f274857ccb58de030d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273049"
---
# <a name="creatormap-structure"></a>CreatorMap — Struktura

Obsługuje infrastrukturę biblioteki szablonów w języku C++ środowisko wykonawcze systemu Windows i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Uwagi

Zawiera informacje o sposobach inicjowania, rejestrowania i wyrejestrowywania obiektów.

`CreatorMap` zawiera następujące informacje:

- Jak inicjować, rejestrować i wyrejestrować obiekty.

- Jak porównać dane aktywacji w zależności od klasycznej fabryki COM lub środowisko wykonawcze systemu Windows.

- Informacje o pamięci podręcznej fabryki i nazwie serwera dla interfejsu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

Nazwa                                          | Opis
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap:: activationId — Członek](#activationid)     | Reprezentuje identyfikator obiektu, który jest identyfikowany za pomocą klasycznego identyfikatora klasy COM lub nazwy środowisko wykonawcze systemu Windows.
[CreatorMap:: factoryCache](#factorycache)     | Przechowuje wskaźnik do pamięci podręcznej fabryki dla `CreatorMap` .
[CreatorMap:: factoryCreator](#factorycreator) | Tworzy fabrykę dla określonego `CreatorMap` .
[CreatorMap:: servername](#servername)         | Przechowuje nazwę serwera dla `CreatorMap` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CreatorMap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="creatormapactivationid"></a><a name="activationid"></a> CreatorMap:: activationId — Członek

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Parametry

*Identyfikator*<br/>
Identyfikator interfejsu.

*getruntimename*<br/>
Funkcja, która pobiera nazwę obiektu środowiska uruchomieniowego systemu Windows.

### <a name="remarks"></a>Uwagi

Reprezentuje identyfikator obiektu, który jest identyfikowany przez klasyczny identyfikator klasy COM lub nazwę środowiska uruchomieniowego systemu Windows.

## <a name="creatormapfactorycache"></a><a name="factorycache"></a> CreatorMap:: factoryCache

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Uwagi

Przechowuje wskaźnik do pamięci podręcznej fabryki dla `CreatorMap` .

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a> CreatorMap:: factoryCreator

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Parametry

*currentflags*<br/>
Jeden z modułów wyliczających [RuntimeClassType —](runtimeclasstype-enumeration.md) .

*Autotekstu*<br/>
CreatorMap.

*iidClassFactory*<br/>
Identyfikator interfejsu fabryki klas.

*indywidual*<br/>
Po zakończeniu operacji adres klasy fabryki klas.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

### <a name="remarks"></a>Uwagi

Tworzy fabrykę dla określonego CreatorMap.

## <a name="creatormapservername"></a><a name="servername"></a> CreatorMap:: servername

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Uwagi

Przechowuje nazwę serwera dla CreatorMap.
