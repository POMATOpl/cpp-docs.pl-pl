---
description: 'Dowiedz się więcej o: module:: ReleaseNotifier, Klasa'
title: Module::ReleaseNotifier — Klasa
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: ebb4d949cbb1e7230894fa24a523e4d6b6cd2657
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186262"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier — Klasa

Wywołuje program obsługi zdarzeń po wydaniu ostatniego obiektu w module.

## <a name="syntax"></a>Składnia

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                                                                | Opis
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module:: ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Deinicjalizuje bieżące wystąpienie `Module::ReleaseNotifier` klasy.
[Module:: ReleaseNotifier:: ReleaseNotifier](#releasenotifier-releasenotifier)        | Inicjuje nowe wystąpienie klasy `Module::ReleaseNotifier`.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                         | Opis
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module:: ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | Po zaimplementowaniu program wywołuje procedurę obsługi zdarzeń, gdy ostatni obiekt w module zostanie wydaną.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Usuwa bieżący `Module::ReleaseNotifier` obiekt, jeśli obiekt został skonstruowany za pomocą parametru **`true`** .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ReleaseNotifier`

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a> Module:: ReleaseNotifier:: ~ ReleaseNotifier

Deinicjalizuje bieżące wystąpienie `Module::ReleaseNotifier` klasy.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a> Module:: ReleaseNotifier:: Invoke

Po zaimplementowaniu program wywołuje procedurę obsługi zdarzeń, gdy ostatni obiekt w module zostanie wydaną.

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a> Module:: ReleaseNotifier:: Release

Usuwa bieżący `Module::ReleaseNotifier` obiekt, jeśli obiekt został skonstruowany za pomocą parametru **`true`** .

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a> Module:: ReleaseNotifier:: ReleaseNotifier

Inicjuje nowe wystąpienie klasy `Module::ReleaseNotifier`.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parametry

*Usuwanie*<br/>
**`true`** Aby usunąć to wystąpienie, gdy `Release` wywoływana jest metoda; **`false`** aby nie usuwać tego wystąpienia.
