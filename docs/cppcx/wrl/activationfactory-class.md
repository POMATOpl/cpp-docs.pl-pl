---
description: 'Dowiedz się więcej na temat: Klasa ActivationFactory'
title: ActivationFactory — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 7204a3c2f981947a03efba648dd91b69d582fee1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287843"
---
# <a name="activationfactory-class"></a>ActivationFactory — Klasa

Umożliwia aktywowanie co najmniej jednej klasy przez środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Parametry

*I0*<br/>
Interfejs zerowego.

*Elementem I1*<br/>
Pierwszy interfejs.

*I2*<br/>
Drugi interfejs.

## <a name="remarks"></a>Uwagi

`ActivationFactory` zapewnia metody rejestracji i podstawowe funkcje `IActivationFactory` interfejsu. `ActivationFactory` umożliwia również zapewnienie niestandardowej implementacji fabryki.

Poniższy fragment kodu symbolicznie ilustruje sposób używania ActivationFactory.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

Poniższy fragment kodu przedstawia sposób użycia struktury [implementującej](implements-structure.md) , aby określić więcej niż trzy identyfikatory interfejsów.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                                       | Opis
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory:: ActivationFactory](#activationfactory) | Inicjuje `ActivationFactory` klasę.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                           | Opis
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory:: AddRef](#addref)                           | Zwiększa liczbę odwołań bieżącego `ActivationFactory` obiektu.
[ActivationFactory:: GetIids —](#getiids)                         | Pobiera tablicę zaimplementowanych identyfikatorów interfejsów.
[ActivationFactory:: GetRuntimeClassName —](#getruntimeclassname) | Pobiera nazwę klasy środowiska uruchomieniowego obiektu, który tworzy bieżące `ActivationFactory` wystąpienia.
[ActivationFactory:: GetTrustLevel](#gettrustlevel)             | Pobiera poziom zaufania obiektu, który jest bieżącym `ActivationFactory` wystąpieniem.
[ActivationFactory:: QueryInterface](#queryinterface)           | Pobiera wskaźnik do określonego interfejsu.
[ActivationFactory:: Release](#release)                         | Zmniejsza liczbę odwołań bieżącego `ActivationFactory` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a> ActivationFactory:: ActivationFactory

Inicjuje `ActivationFactory` klasę.

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a> ActivationFactory:: AddRef

Zwiększa liczbę odwołań bieżącego `ActivationFactory` obiektu.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wartość HRESULT, która opisuje awarię.

## <a name="activationfactorygetiids"></a><a name="getiids"></a> ActivationFactory:: GetIids —

Pobiera tablicę zaimplementowanych identyfikatorów interfejsów.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametry

*IidCount —*<br/>
Po zakończeniu tej operacji liczba identyfikatorów interfejsu w tablicy *IID* .

*IID*<br/>
Po zakończeniu tej operacji tablica zaimplementowanych identyfikatorów interfejsów.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wartość HRESULT, która opisuje awarię. E_OUTOFMEMORY to możliwe niepowodzenie HRESULT.

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a> ActivationFactory:: GetRuntimeClassName —

Pobiera nazwę klasy środowiska uruchomieniowego obiektu, który tworzy bieżące `ActivationFactory` wystąpienia.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Parametry

*Nr środowiska uruchomieniowego*<br/>
Po zakończeniu tej operacji, dojście do ciągu, który zawiera nazwę klasy środowiska uruchomieniowego obiektu, który tworzy bieżące `ActivationFactory` wystąpienia.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wartość HRESULT, która opisuje awarię.

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a> ActivationFactory:: GetTrustLevel

Pobiera poziom zaufania obiektu, który jest bieżącym `ActivationFactory` wystąpieniem.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Parametry

*trustLvl*<br/>
Po zakończeniu tej operacji poziom zaufania klasy środowiska uruchomieniowego, który `ActivationFactory` tworzy wystąpienia.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie błąd potwierdzenia jest emitowany, a *trustLvl* jest ustawiony na `FullTrust` .

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a> ActivationFactory:: QueryInterface

Pobiera wskaźnik do określonego interfejsu.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametry

*riid*<br/>
Identyfikator interfejsu.

*ppvObject*<br/>
Po zakończeniu tej operacji wskaźnik do interfejsu określony przez parametr *riid*.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wartość HRESULT, która opisuje awarię.

## <a name="activationfactoryrelease"></a><a name="release"></a> ActivationFactory:: Release

Zmniejsza liczbę odwołań bieżącego `ActivationFactory` obiektu.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wartość HRESULT, która opisuje awarię.
