---
description: 'Dowiedz się więcej o: module:: GenericReleaseNotifier, Klasa'
title: Module::GenericReleaseNotifier — Klasa
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
ms.openlocfilehash: dd82da7c1b6b9a77c68b6d451bfa6dac31f51180
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186379"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier — Klasa

Wywołuje program obsługi zdarzeń po wydaniu ostatniego obiektu w bieżącym module. Procedura obsługi zdarzeń jest określana na podstawie wyrażenia lambda, Funktor lub wskaźnika do funkcji.

## <a name="syntax"></a>Składnia

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ elementu członkowskiego danych, który zawiera lokalizację programu obsługi zdarzeń.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                                                                                     | Opis
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: GenericReleaseNotifier](#genericreleasenotifier-genericreleasenotifier) | Inicjuje nowe wystąpienie klasy `Module::GenericReleaseNotifier`.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                                     | Opis
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: Invoke](#genericreleasenotifier-invoke) | Wywołuje procedurę obsługi zdarzeń skojarzoną z bieżącym `Module::GenericReleaseNotifier` obiektem.

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

Nazwa                                                                          | Opis
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: callback_](#genericreleasenotifier-callback) | Przechowuje procedurę obsługi zdarzeń lambda, Funktor lub wskaźnika do funkcji skojarzoną z bieżącym `Module::GenericReleaseNotifier` obiektem.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a> Module:: GenericReleaseNotifier:: callback_

Przechowuje procedurę obsługi zdarzeń lambda, Funktor lub wskaźnika do funkcji skojarzoną z bieżącym `Module::GenericReleaseNotifier` obiektem.

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a> Module:: GenericReleaseNotifier:: GenericReleaseNotifier

Inicjuje nowe wystąpienie klasy `Module::GenericReleaseNotifier`.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Parametry

*wywołania zwrotnego*<br/>
Procedura obsługi zdarzeń lambda, Funktor lub wskaźnika do funkcji, która może być wywoływana z operatorem funkcji nawiasów ( `()` ).

*Usuwanie*<br/>
Określ **`true`** , aby włączyć wywoływanie źródłowego [modułu:: ReleaseNotifier:: Release ()](module-releasenotifier-class.md#releasenotifier-release) ; w przeciwnym razie Określ **`false`** .

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a> Module:: GenericReleaseNotifier:: Invoke

Wywołuje procedurę obsługi zdarzeń skojarzoną z bieżącym `Module::GenericReleaseNotifier` obiektem.

```cpp
void Invoke();
```
