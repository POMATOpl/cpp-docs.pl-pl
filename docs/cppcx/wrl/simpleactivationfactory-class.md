---
description: 'Dowiedz się więcej na temat: Klasa SimpleActivationFactory'
title: SimpleActivationFactory — Klasa
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 83643c69977b887e58e430bbd500fcf7c2e81ca6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135216"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory — Klasa

Zapewnia podstawowy mechanizm tworzenia środowisko wykonawcze systemu Windows lub klasycznej klasy bazowej modelu COM.

## <a name="syntax"></a>Składnia

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Parametry

*Opiera*<br/>
Klasa bazowa.

## <a name="remarks"></a>Uwagi

Klasa bazowa musi udostępniać Konstruktor domyślny.

Poniższy przykład kodu demonstruje, jak używać SimpleActivationFactory z makrem [ActivatableClassWithFactoryEx](activatableclass-macros.md) .

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance, metoda](#activateinstance)|Tworzy wystąpienie określonego interfejsu.|
|[SimpleActivationFactory::GetRuntimeClassName, metoda](#getruntimeclassname)|Pobiera nazwę klasy środowiska uruchomieniowego wystąpienia klasy określonej przez parametr szablonu klasy *bazowej* .|
|[SimpleActivationFactory::GetTrustLevel, metoda](#gettrustlevel)|Pobiera poziom zaufania wystąpienia klasy określonej przez parametr szablonu klasy *bazowej* .|

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

`SimpleActivationFactory`

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a> SimpleActivationFactory:: ActivateInstance —, Metoda

Tworzy wystąpienie określonego interfejsu.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Parametry

*ppvObject*<br/>
Po zakończeniu tej operacji wskaźnik do wystąpienia obiektu określonego przez `Base` parametr szablonu klasy.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

### <a name="remarks"></a>Uwagi

Jeśli `__WRL_STRICT__` jest zdefiniowany, błąd potwierdzenia jest emitowany, jeśli klasa bazowa określona w parametrze szablonu klasy nie pochodzi od [RuntimeClass](runtimeclass-class.md)lub nie została skonfigurowana przy użyciu wartości wyliczenia WinRT lub WinRtClassicComMix [RuntimeClassType —](runtimeclasstype-enumeration.md) .

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a> SimpleActivationFactory:: GetRuntimeClassName —, Metoda

Pobiera nazwę klasy środowiska uruchomieniowego wystąpienia klasy określonej przez `Base` parametr szablonu klasy.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Parametry

*Nr środowiska uruchomieniowego*<br/>
Po zakończeniu tej operacji nazwa klasy środowiska uruchomieniowego.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

### <a name="remarks"></a>Uwagi

Jeśli `__WRL_STRICT__` jest zdefiniowany, błąd potwierdzenia jest emitowany, jeśli Klasa określona przez `Base` parametr szablonu klasy nie pochodzi od [RuntimeClass](runtimeclass-class.md)lub nie została skonfigurowana przy użyciu wartości wyliczenia WinRT lub WinRtClassicComMix [RuntimeClassType —](runtimeclasstype-enumeration.md) .

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a> SimpleActivationFactory:: GetTrustLevel, Metoda

Pobiera poziom zaufania wystąpienia klasy określonej przez `Base` parametr szablonu klasy.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Parametry

*trustLvl*<br/>
Gdy ta operacja zostanie ukończona, poziom zaufania bieżącego obiektu klasy.

### <a name="return-value"></a>Wartość zwracana

Zawsze S_OK.
