---
description: 'Dowiedz się więcej o programie: przestrzeń nazw platformy (C++/CX)'
title: Przestrzeń nazw platformy (C++/CX)
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- Platform/Platform
helpviewer_keywords:
- Platform Namespace (C++/CX)
ms.assetid: b160e822-d424-43d2-ba60-57b0e81f259c
ms.openlocfilehash: 80f1b82ed39212812c8d316d4b7de09bf20ccad8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308318"
---
# <a name="platform-namespace-ccx"></a>Przestrzeń nazw platformy (C++/CX)

Zawiera wbudowane typy, które są zgodne z środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
using namespace Platform;
```

### <a name="members"></a>Elementy członkowskie

**Atrybuty**

Przestrzeń nazw platformy zawiera atrybuty, klasy, wyliczenia, interfejsy i struktury. Platforma zawiera również zagnieżdżone przestrzenie nazw.

|Atrybut|Opis|
|---------------|-----------------|
|Flagi|Wskazuje, że Wyliczenie może być traktowane jako pole bitowe; oznacza to zestaw flag.|
|MTAThread|Wskazuje, że model wątkowości dla aplikacji jest apartamentem wielowątkowym (MTA).|
|STAThread|Wskazuje, że model wątkowości dla aplikacji jest apartamentem jednowątkowym (STA).|

**Klasy**

Przestrzeń nazw platformy ma następujące klasy.

|Klasa|Opis|
|-----------|-----------------|
|[Platform:: AccessDeniedException, Klasa](../cppcx/platform-accessdeniedexception-class.md)|Uruchamiany w przypadku odmowy dostępu do zasobu lub funkcji.|
|[Platform:: Agile — Klasa](../cppcx/platform-agile-class.md)|Reprezentuje obiekt nieagile jako obiekt Agile.|
|[Platform:: Array, Klasa](../cppcx/platform-array-class.md)|Przedstawia tablicę jednowymiarową, modyfikowalną do edycji.|
|[Platform:: ArrayReference, Klasa](../cppcx/platform-arrayreference-class.md)|Reprezentuje tablicę, której Inicjalizacja jest zoptymalizowana pod kątem minimalizowania operacji kopiowania.|
|[Platform:: Box — Klasa](../cppcx/platform-box-class.md)|Używane do deklarowania typu opakowanego, który hermetyzuje typ wartości, taki jak Windows:: Foundation::D ateTime lub Int64, gdy ten typ jest przesyłany przez interfejs binarny aplikacji (ABI) lub przechowywany w zmiennej typu [platform:: Object ^](../cppcx/platform-object-class.md).|
|[Platform:: ChangedStateException, Klasa](../cppcx/platform-changedstateexception-class.md)|Zgłaszany, gdy metody iteratora kolekcji lub widok kolekcji są wywoływane po zmianie kolekcji nadrzędnej, unieważnienie wyników metody.|
|[Platform:: ClassNotRegisteredException, Klasa](../cppcx/platform-classnotregisteredexception-class.md)|Zgłaszany, gdy nie zarejestrowano klasy COM.|
|[Platform:: COMException, Klasa](../cppcx/platform-comexception-class.md)|Reprezentuje wyjątek, który jest generowany, gdy Nierozpoznana wartość jest zwracana z wywołania metody COM.|
|[Platforma::D Klasa elegata](../cppcx/platform-delegate-class.md)|Reprezentuje sygnaturę funkcji wywołania zwrotnego.|
|[Platforma::D isconnectobject Class](../cppcx/platform-disconnectedexception-class.md)|Obiekt został odłączony od swoich klientów.|
|[Platform:: Exception, Klasa](../cppcx/platform-exception-class.md)|Reprezentuje błędy występujące podczas wykonywania aplikacji. Klasa bazowa dla wyjątków.|
|[Platform:: FailureException, Klasa](../cppcx/platform-failureexception-class.md)|Zgłaszany, gdy operacja zakończyła się niepowodzeniem. Jest to odpowiednik E_FAIL HRESULT.|
|[Klasa wartości Platform::Guid](../cppcx/platform-guid-value-class.md)|Reprezentuje identyfikator GUID w systemie typu środowisko wykonawcze systemu Windows.|
|[Platform:: InvalidArgumentException, Klasa](../cppcx/platform-invalidargumentexception-class.md)|Zgłaszany, gdy jeden z argumentów dostarczonych do metody jest nieprawidłowy.|
|[Platform:: InvalidCastException, Klasa](../cppcx/platform-invalidcastexception-class.md)|Zgłoszone w przypadku nieprawidłowego rzutowania lub konwersji jawnej.|
|[Platform:: MTAThreadAttribute, Klasa](../cppcx/platform-mtathreadattribute-class.md)|Wskazuje, że model wątkowości dla aplikacji jest apartamentem wielowątkowym (MTA).|
|[Platform:: NotImplementedException, Klasa](../cppcx/platform-notimplementedexception-class.md)|Zgłaszany, jeśli metoda interfejsu nie została zaimplementowana w klasie.|
|[Platform:: NullReferenceException, Klasa](../cppcx/platform-nullreferenceexception-class.md)|Zgłaszany, gdy istnieje próba odwołująca się do odwołania do obiektu o wartości null.|
|[Platform:: Object — Klasa](../cppcx/platform-object-class.md)|Klasa bazowa, która zapewnia typowe zachowanie.|
|[Platform:: ObjectDisposedException, Klasa](../cppcx/platform-objectdisposedexception-class.md)|Zgłaszany, gdy operacja jest wykonywana na usuniętym obiekcie.|
|[Platform:: OperationCanceledException, Klasa](../cppcx/platform-operationcanceledexception-class.md)|Zgłaszany, gdy operacja zostanie przerwana.|
|[Platform:: OutOfBoundsException, Klasa](../cppcx/platform-outofboundsexception-class.md)|Zgłaszany, gdy operacja próbuje uzyskać dostęp do danych poza prawidłowym zakresem.|
|[Platform:: OutOfMemoryException, Klasa](../cppcx/platform-outofmemoryexception-class.md)|Zgłaszany, gdy jest za mało pamięci, aby ukończyć operację.|
|[Platform:: STAThreadAttribute, Klasa](../cppcx/platform-stathreadattribute-class.md)|Wskazuje, że model wątkowości dla aplikacji jest apartamentem jednowątkowym (STA).|
|[Platform:: String — Klasa](../cppcx/platform-string-class.md)|Sekwencyjna kolekcja znaków Unicode, która jest używana do reprezentowania tekstu.|
|[Platform:: StringReference, Klasa](../cppcx/platform-stringreference-class.md)|Umożliwia dostęp do buforów ciągów z minimalnym obciążeniem kopiowania.|
|[Platform:: Type — Klasa](../cppcx/platform-type-class.md)|Identyfikuje typ wbudowany przez Wyliczenie kategorii.|
|[Platform:: ValueType, Klasa](../cppcx/platform-valuetype-class.md)|Klasa bazowa dla wystąpień typów wartości.|
|[Platform:: WeakReference, Klasa](../cppcx/platform-weakreference-class.md)|Zapewnia słabe odwołanie do obiektów klasy referencyjnej, które nie zwiększają liczby odwołań.|
|[Platform:: WriteOnlyArray, Klasa](../cppcx/platform-writeonlyarray-class.md)|Reprezentuje jednowymiarową tablicę tylko do zapisu, która jest używana jako parametr wejściowy metod implementujących wzorzec metodzie FillArray.|
|[Platform:: WrongThreadException, Klasa](../cppcx/platform-wrongthreadexception-class.md)|Zgłaszany, gdy wątek wywołuje za pośrednictwem wskaźnika interfejsu, który jest przeznaczony dla obiektu serwera proxy, który nie należy do Apartament wątku.|

**Implementacje interfejsu**

Przestrzeń nazw platformy definiuje następujące interfejsy.

|Interfejs|Opis|
|---------------|-----------------|
|[Platform:: IBox, interfejs](../cppcx/platform-ibox-interface.md)|Służy do przekazywania typów wartości do funkcji, których parametry są wpisane jako platform:: Object ^.|
|[Platform:: IBoxArray, interfejs](../cppcx/platform-iboxarray-interface.md)|Interfejs używany do przekazywania tablic typów wartości do funkcji, których parametry są wpisane jako platform:: Array.|
|[Platform:: IDisposable, interfejs](../cppcx/platform-idisposable-interface.md)|Używane do zwalniania niezarządzanych zasobów.|

**Wyliczenia**

Przestrzeń nazw platformy ma następujące wyliczenia.

|Interfejs|Opis|
|---------------|-----------------|
|[Platform::CallbackContext, wyliczenie](../cppcx/platform-callbackcontext-enumeration.md)|Wyliczenie, które jest używane jako parametr konstruktora delegata. Określa, czy wywołanie zwrotne ma zostać rozkierowany do wątku źródłowego lub do wątku wywołującego.|
|[Platform::TypeCode, wyliczenie](../cppcx/platform-typecode-enumeration.md)|Określa kategorię liczbową reprezentującą typ wbudowany.|

**Struktury**

Przestrzeń nazw platformy ma następujące struktury.

|Struktura|Opis|
|---------------|-----------------|
|[Platform:: enum, Klasa](../cppcx/platform-enum-class.md)|Reprezentuje nazwaną stałą.|
|[Klasa wartości Platform::Guid](../cppcx/platform-guid-value-class.md)|Reprezentuje identyfikator GUID.|
|[Klasa wartości Platform::IntPtr](../cppcx/platform-intptr-value-class.md)|Podpisany wskaźnik, którego rozmiar jest odpowiedni dla platformy (32-bitowy lub 64-bitowy).|
|[Klasa wartości Platform::SizeT](../cppcx/platform-sizet-value-class.md)|Typ danych bez znaku służący do reprezentowania rozmiaru obiektu.|
|[Klasa wartości Platform::UIntPtr](../cppcx/platform-uintptr-value-class.md)|Niepodpisany wskaźnik, którego rozmiar jest odpowiedni dla platformy (32-bitowy lub 64-bitowy).|

## <a name="see-also"></a>Zobacz też

[Platform:: Collections, przestrzeń nazw](../cppcx/platform-collections-namespace.md)<br/>
[Platform:: Runtime:: CompilerServices, przestrzeń nazw](../cppcx/platform-runtime-compilerservices-namespace.md)<br/>
[Platform:: Runtime:: InteropServices, przestrzeń nazw](../cppcx/platform-runtime-interopservices-namespace.md)<br/>
[Platform:: Metadata — przestrzeń nazw](../cppcx/platform-metadata-namespace.md)
