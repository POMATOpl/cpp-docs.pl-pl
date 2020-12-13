---
description: 'Dowiedz się więcej na temat: Microsoft:: WRL, przestrzeń nazw'
title: Microsoft::WRL — Przestrzeń nazw
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL
- module/Microsoft::WRL
- async/Microsoft::WRL
- internal/Microsoft::WRL
- event/Microsoft::WRL
- ftm/Microsoft::WRL
- client/Microsoft::WRL
- corewrappers/Microsoft::WRL
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
ms.openlocfilehash: fdf7f0fbdca5cd5d95772052dd5dfb5018cabb18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335542"
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL — Przestrzeń nazw

Definiuje podstawowe typy, które tworzą środowisko wykonawcze systemu Windows biblioteki szablonów C++.

## <a name="syntax"></a>Składnia

```cpp
namespace Microsoft::WRL;
```

## <a name="members"></a>Elementy członkowskie

### <a name="typedefs"></a>Typedefs

|Nazwa|Opis|
|----------|-----------------|
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt | InhibitWeakReference>`|

### <a name="classes"></a>Klasy

|Nazwa|Opis|
|----------|-----------------|
|[Klasa ActivationFactory](activationfactory-class.md)|Umożliwia aktywowanie co najmniej jednej klasy przez środowisko wykonawcze systemu Windows.|
|[Klasa AsyncBase](asyncbase-class.md)|Implementuje asynchroniczną maszynę stanu środowisko wykonawcze systemu Windows.|
|[Klasa ClassFactory](classfactory-class.md)|Implementuje podstawowe funkcje `IClassFactory` interfejsu.|
|[Klasa ComPtr](comptr-class.md)|Tworzy *inteligentny wskaźnik* typu, który reprezentuje interfejs określony przez parametr szablonu. ComPtr automatycznie utrzymuje liczbę odwołań dla podstawowego wskaźnika interfejsu i zwalnia interfejs, gdy liczba odwołań spadnie do zera.|
|[Klasa DeferrableEventArgs](deferrableeventargs-class.md)|Klasa szablonu używana dla typów argumentów zdarzeń dla odroczeń.|
|[EventSource — Klasa](eventsource-class.md)|Reprezentuje zdarzenie. `EventSource` funkcje elementów członkowskich Dodaj, Usuń i Wywołaj procedury obsługi zdarzeń.|
|[Klasa FtmBase](ftmbase-class.md)|Reprezentuje obiekt organizatora wolnego wątku.|
|[Klasa modułu](module-class.md)|Reprezentuje kolekcję obiektów pokrewnych.|
|[Klasa RuntimeClass](runtimeclass-class.md)|Reprezentuje klasę wystąpienia, która dziedziczy określoną liczbę interfejsów i udostępnia określony środowisko wykonawcze systemu Windows, klasyczny COM i słabe wsparcie referencyjne.|
|[Klasa SimpleActivationFactory](simpleactivationfactory-class.md)|Zapewnia podstawowy mechanizm tworzenia środowisko wykonawcze systemu Windows lub klasycznej klasy bazowej modelu COM.|
|[Klasa SimpleClassFactory](simpleclassfactory-class.md)|Zapewnia podstawowy mechanizm tworzenia klasy bazowej.|
|[Klasa WeakRef](weakref-class.md)|Reprezentuje *słabe odwołanie* , które może być używane tylko przez środowisko wykonawcze systemu Windows, a nie klasyczny com. Słabe odwołanie reprezentuje obiekt, który może lub nie jest dostępny.|

### <a name="structures"></a>Struktury

|Nazwa|Opis|
|----------|-----------------|
|[ChainInterfaces — Struktura](chaininterfaces-structure.md)|Określa funkcje weryfikacji i inicjowania, które mogą być stosowane do zestawu identyfikatorów interfejsów.|
|[CloakedIid — Struktura](cloakediid-structure.md)|Wskazuje `RuntimeClass` , `Implements` i szablony, `ChainInterfaces` których określony interfejs nie jest dostępny na liście IID.|
|[Implements, struktura](implements-structure.md)|Implementuje `QueryInterface` i `GetIid` dla określonych interfejsów.|
|[MixIn — Struktura](mixin-structure.md)|Zapewnia, że Klasa środowiska uruchomieniowego pochodzi z interfejsów środowisko wykonawcze systemu Windows, jeśli istnieje, a następnie do klasycznych interfejsów COM.|
|[RuntimeClassFlags, struktura](runtimeclassflags-structure.md)|Zawiera typ wystąpienia elementu [RuntimeClass](runtimeclass-class.md).|

### <a name="enumerations"></a>Wyliczenia

|Nazwa|Opis|
|----------|-----------------|
|[AsyncResultType, wyliczenie](asyncresulttype-enumeration.md)|Określa typ wyniku zwróconego przez `GetResults()` metodę.|
|[ModuleType, wyliczenie](moduletype-enumeration.md)|Określa, czy moduł powinien obsługiwać serwer w toku, czy też poza procesem.|
|[RuntimeClassType, wyliczenie](runtimeclasstype-enumeration.md)|Określa typ wystąpienia [RuntimeClass](runtimeclass-class.md) , które jest obsługiwane.|

### <a name="functions"></a>Funkcje

|Nazwa|Opis|
|----------|-----------------|
|[AsWeak —, funkcja](asweak-function.md)|Pobiera słabe odwołanie do określonego wystąpienia.|
|[Funkcja wywołania zwrotnego (WRL)](callback-function-wrl.md)|Tworzy obiekt, którego funkcja członkowska jest metodą wywołania zwrotnego.|
|[CreateActivationFactory —, funkcja](createactivationfactory-function.md)|Tworzy fabrykę, która tworzy wystąpienia określonej klasy, które mogą być aktywowane przez środowisko wykonawcze systemu Windows.|
|[CreateClassFactory —, funkcja](createclassfactory-function.md)|Tworzy fabrykę, która tworzy wystąpienia określonej klasy.|
|[Utwórz funkcję](make-function.md)|Inicjuje określoną klasę środowisko wykonawcze systemu Windows.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** Async. h, Client. h, corewrappers. h, Event. h, FTM. h, implementuje. h, Internal. h, module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL:: Otoke — przestrzeń nazw](microsoft-wrl-wrappers-namespace.md)
