---
description: Dowiedz się więcej o usłudze Key WRL interfejsy API według kategorii
title: Kluczowe interfejsy API biblioteki WRL według kategorii
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: 14b5e113cb5553227f452d217a1745cbf20a5757
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298919"
---
# <a name="key-wrl-apis-by-category"></a>Kluczowe interfejsy API biblioteki WRL według kategorii

W poniższej tabeli wymieniono podstawowe klasy, struktury, funkcje i makra biblioteki szablonów języka C++ środowisko wykonawcze systemu Windows. Konstrukcje w przestrzeniach nazw pomocnika i klasach zostały pominięte. Te listy rozszerzają dokumentację interfejsu API, która jest uporządkowana według przestrzeni nazw.

## <a name="classes"></a>Klasy

|Tytuł|Opis|
|-----------|-----------------|
|[Klasa ActivationFactory](activationfactory-class.md)|Umożliwia aktywowanie co najmniej jednej klasy przez środowisko wykonawcze systemu Windows.|
|[Klasa AsyncBase](asyncbase-class.md)|Implementuje asynchroniczną maszynę stanu środowisko wykonawcze systemu Windows.|
|[Klasa ClassFactory](classfactory-class.md)|Implementuje podstawowe funkcje `IClassFactory` interfejsu.|
|[Klasa ComPtr](comptr-class.md)|Tworzy *inteligentny wskaźnik* typu, który reprezentuje interfejs określony przez parametr szablonu. ComPtr automatycznie utrzymuje liczbę odwołań dla podstawowego wskaźnika interfejsu i zwalnia interfejs, gdy liczba odwołań spadnie do zera.|
|[Event, klasa (Biblioteka szablonów języka C++ środowiska uruchomieniowego systemu Windows)](event-class-wrl.md)|Reprezentuje zdarzenie.|
|[EventSource — Klasa](eventsource-class.md)|Reprezentuje zdarzenie. `EventSource` funkcje elementów członkowskich Dodaj, Usuń i Wywołaj procedury obsługi zdarzeń.|
|[Klasa FtmBase](ftmbase-class.md)|Reprezentuje obiekt organizatora wolnego wątku.|
|[Obsługa klasy](handlet-class.md)|Reprezentuje dojście do obiektu.|
|[Klasa HString](hstring-class.md)|Zapewnia obsługę manipulowania dojściami HSTRING.|
|[Klasa HStringReference](hstringreference-class.md)|Reprezentuje element HSTRING, który jest tworzony na podstawie istniejącego ciągu.|
|[Klasa modułu](module-class.md)|Reprezentuje kolekcję obiektów pokrewnych.|
|[Module:: GenericReleaseNotifier, Klasa](module-genericreleasenotifier-class.md)|Wywołuje program obsługi zdarzeń po wydaniu ostatniego obiektu w bieżącym module. Procedura obsługi zdarzeń jest określana na podstawie wyrażenia lambda, Funktor lub wskaźnika do funkcji.|
|[Module:: MethodReleaseNotifier, Klasa](module-methodreleasenotifier-class.md)|Wywołuje program obsługi zdarzeń po wydaniu ostatniego obiektu w bieżącym module. Program obsługi zdarzeń jest określany przez obiekt i jego element członkowski typu wskaźnik-a-metoda.|
|[Module:: ReleaseNotifier, Klasa](module-releasenotifier-class.md)|Wywołuje program obsługi zdarzeń po wydaniu ostatniego obiektu w module.|
|[Klasa RoInitializeWrapper](roinitializewrapper-class.md)|Inicjuje środowisko wykonawcze systemu Windows.|
|[Klasa RuntimeClass](runtimeclass-class.md)|Reprezentuje klasę wystąpienia, która dziedziczy określoną liczbę interfejsów i udostępnia określony środowisko wykonawcze systemu Windows, klasyczny COM i słabe wsparcie referencyjne.|
|[Klasa SimpleActivationFactory](simpleactivationfactory-class.md)|Zapewnia podstawowy mechanizm tworzenia środowisko wykonawcze systemu Windows lub klasycznej klasy bazowej modelu COM.|
|[Klasa SimpleClassFactory](simpleclassfactory-class.md)|Zapewnia podstawowy mechanizm tworzenia klasy bazowej.|
|[Klasa WeakRef](weakref-class.md)|Reprezentuje *słabe odwołanie* , które może być używane tylko przez środowisko wykonawcze systemu Windows, a nie klasyczny com. Słabe odwołanie reprezentuje obiekt, który może lub nie jest dostępny.|

## <a name="structures"></a>Struktury

|Tytuł|Opis|
|-----------|-----------------|
|[ChainInterfaces — Struktura](chaininterfaces-structure.md)|Określa funkcje weryfikacji i inicjowania, które mogą być stosowane do zestawu identyfikatorów interfejsów.|
|[CloakedIid — Struktura](cloakediid-structure.md)|Wskazuje `RuntimeClass` , `Implements` i szablony, `ChainInterfaces` których określony interfejs nie jest dostępny na liście IID.|
|[Implements, struktura](implements-structure.md)|Implementuje `QueryInterface` i `GetIid` dla określonych interfejsów.|
|[MixIn — Struktura](mixin-structure.md)|Zapewnia, że Klasa środowiska uruchomieniowego pochodzi z interfejsów środowisko wykonawcze systemu Windows, jeśli istnieje, a następnie do klasycznych interfejsów COM.|

## <a name="functions"></a>Funkcje

|Tytuł|Opis|
|-----------|-----------------|
|[ActivateInstance —, funkcja](activateinstance-function.md)|Rejestruje i Pobiera wystąpienie określonego typu zdefiniowane w określonym IDENTYFIKATORze klasy.|
|[AsWeak —, funkcja](asweak-function.md)|Pobiera słabe odwołanie do określonego wystąpienia.|
|[Funkcja wywołania zwrotnego](callback-function-wrl.md)|Tworzy obiekt, którego funkcja członkowska jest metodą wywołania zwrotnego.|
|[CreateActivationFactory —, funkcja](createactivationfactory-function.md)|Tworzy fabrykę, która tworzy wystąpienia określonej klasy, które mogą być aktywowane przez środowisko wykonawcze systemu Windows.|
|[CreateClassFactory —, funkcja](createclassfactory-function.md)|Tworzy fabrykę, która tworzy wystąpienia określonej klasy.|
|[GetActivationFactory —, funkcja](getactivationfactory-function.md)|Pobiera fabrykę aktywacji dla typu określonego przez parametr szablonu.|
|[Utwórz funkcję](make-function.md)|Inicjuje określoną klasę środowisko wykonawcze systemu Windows.|

## <a name="macros"></a>Makra

|Tytuł|Opis|
|-----------|-----------------|
|[Makra ActivatableClass](activatableclass-macros.md)|Wypełnia wewnętrzną pamięć podręczną, która zawiera fabrykę, która może utworzyć wystąpienie określonej klasy.|
|[InspectableClass — makro](inspectableclass-macro.md)|Ustawia nazwę klasy środowiska uruchomieniowego i poziom zaufania.|

## <a name="see-also"></a>Zobacz też

[Biblioteka szablonów języka C++ środowiska wykonawczego systemu Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)
