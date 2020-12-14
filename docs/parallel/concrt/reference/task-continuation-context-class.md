---
description: Dowiedz się więcej na temat klasy task_continuation_context
title: task_continuation_context — Klasa
ms.date: 11/04/2016
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
ms.openlocfilehash: ff843a84dd3e0bdaeee9df99e91b1708116191d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188303"
---
# <a name="task_continuation_context-class"></a>task_continuation_context — Klasa

`task_continuation_context`Klasa pozwala określić, gdzie mają być kontynuowane. Jest to przydatne tylko w przypadku używania tej klasy z poziomu aplikacji środowisko wykonawcze systemu Windows. W przypadku aplikacji innych niż środowisko wykonawcze systemu Windows kontekst wykonywania kontynuacji zadania jest określany przez środowisko uruchomieniowe i nie można go konfigurować.

## <a name="syntax"></a>Składnia

```cpp
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|Zwraca obiekt kontekstu kontynuacji zadania, który reprezentuje bieżący kontekst wątku WinRT.|
|[use_arbitrary](#use_arbitrary)|Tworzy kontekst kontynuacji zadania, który umożliwia środowisko uruchomieniowe Wybieranie kontekstu wykonywania w celu kontynuacji.|
|[use_current](#use_current)|Zwraca obiekt kontekstu kontynuacji zadania, który reprezentuje bieżący kontekst wykonania.|
|[use_default](#use_default)|Tworzy domyślny kontekst kontynuacji zadania.|
|[use_synchronous_execution](#use_synchronous_execution)|Zwraca obiekt kontekstu kontynuacji zadania, który reprezentuje kontekst wykonania synchronicznego.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ppltasks. h

**Przestrzeń nazw:** współbieżność

## <a name="get_current_winrt_context"></a><a name="get_current_winrt_context"></a> get_current_winrt_context

Zwraca obiekt kontekstu kontynuacji zadania, który reprezentuje bieżący kontekst wątku WinRT.

### <a name="syntax"></a>Składnia

```cpp
static task_continuation_context get_current_winrt_context();
```

### <a name="return-value"></a>Wartość zwracana

Bieżący kontekst wątku środowisko wykonawcze systemu Windows. Zwraca puste task_continuation_context, jeśli wywołano z kontekstu nieśrodowisko wykonawcze systemu Windowsowego.

### <a name="remarks"></a>Uwagi

`get_current_winrt_context`Metoda przechwytuje kontekst wątku środowisko wykonawcze systemu Windows obiektu wywołującego. Zwraca pusty kontekst do obiektów wywołujących innych niż środowisko wykonawcze systemu Windows.

Wartość zwracana przez `get_current_winrt_context` może służyć do wskazania, że środowisko uruchomieniowe powinno być wykonywane w modelu apartamentu przechwyconego kontekstu (sta vs MTA), bez względu na to, czy zadanie poprzedzające jest oparte na komórce. Zadanie z obsługą apartamentu to zadanie, które odpakuje `IAsyncInfo` interfejs środowisko wykonawcze systemu Windows lub zadanie, które jest z tego zadania podrzędnego.

Ta metoda jest podobna do  `use_current` metody, ale jest również dostępna dla natywnego kodu c++ bez obsługi rozszerzenia c++/CX. Jest ona przeznaczona do użycia przez zaawansowanych użytkowników, pisząc kod biblioteki C++/CX-agnostic dla obiektów wywołujących natywnych i środowisko wykonawcze systemu Windows. Jeśli ta funkcja jest niezbędna, zalecamy `use_current` metodę, która jest dostępna tylko dla klientów C++/CX.

## <a name="use_arbitrary"></a><a name="use_arbitrary"></a> use_arbitrary

Tworzy kontekst kontynuacji zadania, który umożliwia środowisko uruchomieniowe Wybieranie kontekstu wykonywania w celu kontynuacji.

### <a name="syntax"></a>Składnia

```cpp
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>Wartość zwracana

Kontekst kontynuacji zadania, który reprezentuje arbitralną lokalizację.

### <a name="remarks"></a>Uwagi

Gdy jest używany ten kontekst kontynuacji, kontynuacja będzie wykonywana w kontekście wybranym przez środowisko uruchomieniowe, nawet jeśli zadanie poprzedzające jest zgodne z komórkami.

`use_arbitrary` może służyć do wyłączenia domyślnego zachowania dla kontynuacji w zadaniu typu Apartment, które zostało utworzone w STA.

Ta metoda jest dostępna tylko dla aplikacji środowisko wykonawcze systemu Windows.

## <a name="use_current"></a><a name="use_current"></a> use_current

Zwraca obiekt kontekstu kontynuacji zadania, który reprezentuje bieżący kontekst wykonania.

```cpp
static task_continuation_context use_current();
```

### <a name="return-value"></a>Wartość zwracana

Bieżący kontekst wykonania.

### <a name="remarks"></a>Uwagi

Ta metoda przechwytuje kontekst środowisko wykonawcze systemu Windows obiektu wywołującego, aby kontynuacje mogły być wykonywane w odpowiedniej apartamentie.

Wartość zwracana przez `use_current` może służyć do wskazania środowiska uruchomieniowego, które ma zostać wykonane w przechwyconym kontekście (sta vs MTA), niezależnie od tego, czy zadanie poprzedzające jest zgodne z komórkami. Zadanie z obsługą apartamentu to zadanie, które odpakuje `IAsyncInfo` interfejs środowisko wykonawcze systemu Windows lub zadanie, które jest z tego zadania podrzędnego.

Ta metoda jest dostępna tylko dla aplikacji środowisko wykonawcze systemu Windows.

## <a name="use_default"></a><a name="use_default"></a> use_default

Tworzy domyślny kontekst kontynuacji zadania.

```cpp
static task_continuation_context use_default();
```

### <a name="return-value"></a>Wartość zwracana

Domyślny kontekst kontynuacji.

### <a name="remarks"></a>Uwagi

Domyślny kontekst jest używany, jeśli nie określisz kontekstu kontynuacji podczas wywoływania `then` metody. W aplikacjach systemu Windows dla systemu Windows 7 i nowszych, a także aplikacji klasycznych w systemie Windows 8 lub nowszym, środowisko uruchomieniowe określa, gdzie będą wykonywane kontynuacje zadań. Jednak w aplikacji środowisko wykonawcze systemu Windows domyślny kontekst kontynuacji dla kontynuacji w zadaniu typu Apartment to apartament, gdzie `then` jest wywoływana.

Zadanie z obsługą apartamentu to zadanie, które odpakuje `IAsyncInfo` interfejs środowisko wykonawcze systemu Windows lub zadanie, które jest z tego zadania podrzędnego. W związku z tym w przypadku zaplanowania kontynuacji w zadaniu typu Apartment w środowisko wykonawcze systemu Windows STA, kontynuacja zostanie wykonana w tym STA.

Kontynuacja w zadaniu niezależnym od apartamentu zostanie wykonana w kontekście wybranym przez środowisko uruchomieniowe.

## <a name="task_continuation_contextuse_synchronous_execution"></a><a name="use_synchronous_execution"></a> task_continuation_context:: use_synchronous_execution

Zwraca obiekt kontekstu kontynuacji zadania, który reprezentuje kontekst wykonania synchronicznego.

### <a name="syntax"></a>Składnia

```cpp
static task_continuation_context use_synchronous_execution();
```

### <a name="return-value"></a>Wartość zwracana

Kontekst wykonywania synchronicznego.

### <a name="remarks"></a>Uwagi

`use_synchronous_execution`Metoda wymusza, aby zadanie kontynuacji zostało uruchomione synchronicznie w kontekście, powodując ukończenie jego zadania poprzedzającego.

Jeśli zadanie poprzedzające zostało już zakończone po dołączeniu kontynuacji, kontynuacja przebiega synchronicznie w kontekście, który dołącza kontynuację.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
