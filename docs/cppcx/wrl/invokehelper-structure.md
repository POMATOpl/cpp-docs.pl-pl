---
description: Dowiedz się więcej o strukturze InvokeHelper
title: InvokeHelper — Struktura
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 0b9bb8abb59cce5a3c25d795d0946ffbe88d0076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299023"
---
# <a name="invokehelper-structure"></a>InvokeHelper — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>Parametry

*TDelegateInterface*<br/>
Typ interfejsu delegata.

*TCallback*<br/>
Typ funkcji obsługi zdarzeń.

*argCount*<br/>
Liczba argumentów w `InvokeHelper` specjalizacji.

## <a name="remarks"></a>Uwagi

Zapewnia implementację `Invoke()` metody w oparciu o określoną liczbę i typ argumentów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa     | Opis
-------- | -----------------------------------------------------------------------------
`Traits` | Synonim klasy, która definiuje typ każdego argumentu procedury obsługi zdarzeń.

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                        | Opis
------------------------------------------- | -------------------------------------------------------
[InvokeHelper:: InvokeHelper](#invokehelper) | Inicjuje nowe wystąpienie klasy `InvokeHelper`.

### <a name="public-methods"></a>Metody publiczne

Nazwa                            | Opis
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper:: Invoke](#invoke) | Wywołuje program obsługi zdarzeń, którego podpis zawiera określoną liczbę argumentów.

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

Nazwa                                 | Opis
------------------------------------ | ----------------------------------------------------------
[InvokeHelper:: callback_](#callback) | Reprezentuje procedurę obsługi zdarzeń do wywołania w przypadku wystąpienia zdarzenia.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`InvokeHelper`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="invokehelpercallback_"></a><a name="callback"></a> InvokeHelper:: callback_

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Uwagi

Reprezentuje procedurę obsługi zdarzeń do wywołania w przypadku wystąpienia zdarzenia.

`TCallback`Parametr szablonu określa typ programu obsługi zdarzeń.

## <a name="invokehelperinvoke"></a><a name="invoke"></a> InvokeHelper:: Invoke

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>Parametry

*arg1*<br/>
Argument 1.

*arg2*<br/>
Argument 2.

*arg3*<br/>
Argument 3.

*arg4*<br/>
Argument 4.

*arg5*<br/>
Argument 5.

*arg6*<br/>
Argument 6.

*arg7*<br/>
Argument 7.

*arg8*<br/>
Argument 8.

*arg9*<br/>
Argument 9.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT, który opisuje błąd.

### <a name="remarks"></a>Uwagi

Wywołuje program obsługi zdarzeń, którego podpis zawiera określoną liczbę argumentów.

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a> InvokeHelper:: InvokeHelper

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parametry

*wywołania zwrotnego*<br/>
Procedura obsługi zdarzeń.

### <a name="remarks"></a>Uwagi

Inicjuje nowe wystąpienie klasy `InvokeHelper`.

`TCallback`Parametr szablonu określa typ programu obsługi zdarzeń.
