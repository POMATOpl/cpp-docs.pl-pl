---
description: 'Dowiedz się więcej na temat: Klasa RuntimeClass'
title: RuntimeClass — Klasa
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: f62eec0b5ac9b8fc8ecac390ea07077743fdcb51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330768"
---
# <a name="runtimeclass-class"></a>RuntimeClass — Klasa

Reprezentuje klasę WinRT lub COM, która dziedziczy określone interfejsy i udostępnia określony środowisko wykonawcze systemu Windows, klasyczny COM oraz słabe wsparcie referencyjne.

Ta klasa zapewnia wdrożenie standardowe klas WinRT i com, zapewniając implementację `QueryInterface` , `AddRef` , `Release` itd., zarządza liczbą odwołań modułu i obsługuje dostarczanie fabryki klas dla obiektów aktywowalnej.

## <a name="syntax"></a>Składnia

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Parametry

*classFlags*<br/>
Parametr opcjonalny. Kombinacja co najmniej jednej wartości wyliczenia [RuntimeClassType —](runtimeclasstype-enumeration.md) . `__WRL_CONFIGURATION_LEGACY__`Makro można zdefiniować, aby zmienić wartość domyślną classFlags dla wszystkich klas środowiska uruchomieniowego w projekcie. Jeśli zdefiniowane, wystąpienia RuntimeClass są domyślnie inne niż Agile. Gdy nie jest zdefiniowany, wystąpienia RuntimeClass są domyślnie Agile. Aby uniknąć niejednoznaczności, zawsze Określ wartość `Microsoft::WRL::FtmBase` w `TInterfaces` lub `RuntimeClassType::InhibitFtmBase` . Należy pamiętać, że jeśli są używane zarówno InhibitFtmBase, jak i FtmBase, obiekt będzie Agile.

*TInterfaces*<br/>
Lista interfejsów, które implementuje obiekt `IUnknown` , `IInspectable` lub inne interfejsy kontrolowane przez [RuntimeClassType —](runtimeclasstype-enumeration.md). Może także wystawić inne klasy, z których pochodzą, w szczególności `Microsoft::WRL::FtmBase` Aby obiekt Agile i spowodować jego implementację `IMarshal` .

## <a name="members"></a>Elementy członkowskie

`RuntimeClassInitialize`<br/>
Funkcja, która inicjuje obiekt, jeśli `MakeAndInitialize` Funkcja szablonu jest używana do konstruowania obiektu. Zwraca S_OK, jeśli obiekt został pomyślnie zainicjowany, lub kod błędu COM, jeśli inicjowanie nie powiodło się. Kod błędu COM jest propagowany jako wartość zwracana `MakeAndInitialize` . Należy zauważyć, że `RuntimeClassInitialize` Metoda nie jest wywoływana, jeśli `Make` Funkcja szablonu jest używana do konstruowania obiektu.

### <a name="public-constructors"></a>Konstruktory publiczne

| Nazwa                                               | Opis                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass:: RuntimeClass](#runtimeclass)        | Inicjuje bieżące wystąpienie `RuntimeClass` klasy.   |
| [RuntimeClass:: ~ RuntimeClass](#tilde-runtimeclass) | Deinicjalizuje bieżące wystąpienie `RuntimeClass` klasy. |

### <a name="public-methods"></a>Metody publiczne

| Nazwa                                                      | Opis                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass:: AddRef](#addref)                           | Zwiększa liczbę odwołań dla bieżącego `RuntimeClass` obiektu.                              |
| [RuntimeClass::D ecrementReference](#decrementreference)   | Zmniejsza liczbę odwołań dla bieżącego `RuntimeClass` obiektu.                              |
| [RuntimeClass:: GetIids —](#getiids)                         | Pobiera tablicę, która może zawierać identyfikatory interfejsów zaimplementowane przez bieżący `RuntimeClass` obiekt. |
| [RuntimeClass:: GetRuntimeClassName —](#getruntimeclassname) | Pobiera nazwę klasy środowiska uruchomieniowego bieżącego `RuntimeClass` obiektu.                                  |
| [RuntimeClass:: GetTrustLevel](#gettrustlevel)             | Pobiera poziom zaufania bieżącego `RuntimeClass` obiektu.                                         |
| [RuntimeClass:: Getweakreference —](#getweakreference)       | Pobiera wskaźnik do słabego obiektu referencyjnego dla bieżącego `RuntimeClass` obiektu.                 |
| [RuntimeClass:: InternalAddRef —](#internaladdref)           | Zwiększa liczbę odwołań do bieżącego `RuntimeClass` obiektu.                               |
| [RuntimeClass:: QueryInterface](#queryinterface)           | Pobiera wskaźnik do określonego identyfikatora interfejsu.                                                 |
| [RuntimeClass:: Release](#release)                         | Wykonuje operację wydania modelu COM dla bieżącego `RuntimeClass` obiektu.                             |

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

To jest szczegóły implementacji.

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a> RuntimeClass:: ~ RuntimeClass

Deinicjalizuje bieżące wystąpienie `RuntimeClass` klasy.

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a> RuntimeClass:: AddRef

Zwiększa liczbę odwołań dla bieżącego `RuntimeClass` obiektu.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a> RuntimeClass::D ecrementReference

Zmniejsza liczbę odwołań dla bieżącego `RuntimeClass` obiektu.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

## <a name="runtimeclassgetiids"></a><a name="getiids"></a> RuntimeClass:: GetIids —

Pobiera tablicę, która może zawierać identyfikatory interfejsów zaimplementowane przez bieżący `RuntimeClass` obiekt.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametry

*IidCount —*<br/>
Gdy ta operacja zostanie ukończona, Łączna liczba elementów w tablicy *IID*.

*IID*<br/>
Po zakończeniu tej operacji wskaźnik do tablicy identyfikatorów interfejsów.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie E_OUTOFMEMORY.

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a> RuntimeClass:: GetRuntimeClassName —

Pobiera nazwę klasy środowiska uruchomieniowego bieżącego `RuntimeClass` obiektu.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parametry

*Nr środowiska uruchomieniowego*<br/>
Po zakończeniu tej operacji nazwa klasy środowiska uruchomieniowego.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

### <a name="remarks"></a>Uwagi

Błąd potwierdzenia jest emitowany, jeśli `__WRL_STRICT__` lub `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` nie jest zdefiniowany.

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a> RuntimeClass:: GetTrustLevel

Pobiera poziom zaufania bieżącego `RuntimeClass` obiektu.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parametry

*trustLvl*<br/>
Po zakończeniu tej operacji poziom zaufania bieżącego `RuntimeClass` obiektu.

### <a name="return-value"></a>Wartość zwracana

Zawsze S_OK.

### <a name="remarks"></a>Uwagi

Błąd potwierdzenia jest emitowany, jeśli `__WRL_STRICT__` lub `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` nie jest zdefiniowany.

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a> RuntimeClass:: Getweakreference —

Pobiera wskaźnik do słabego obiektu referencyjnego dla bieżącego `RuntimeClass` obiektu.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Parametry

*weakReference*<br/>
Po zakończeniu tej operacji wskaźnik do słabego obiektu referencyjnego.

### <a name="return-value"></a>Wartość zwracana

Zawsze S_OK.

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a> RuntimeClass:: InternalAddRef —

Zwiększa liczbę odwołań do bieżącego `RuntimeClass` obiektu.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Wartość zwracana

Wynikowy licznik odwołań.

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a> RuntimeClass:: QueryInterface

Pobiera wskaźnik do określonego identyfikatora interfejsu.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametry

*riid*<br/>
Identyfikator interfejsu.

*ppvObject*<br/>
Po zakończeniu tego opereation wskaźnik do interfejsu określonego przez parametr *riid* .

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

## <a name="runtimeclassrelease"></a><a name="release"></a> RuntimeClass:: Release

Wykonuje operację wydania modelu COM dla bieżącego `RuntimeClass` obiektu.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

### <a name="remarks"></a>Uwagi

Jeśli liczba odwołań będzie równa zero, `RuntimeClass` obiekt zostanie usunięty.

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a> RuntimeClass:: RuntimeClass

Inicjuje bieżące wystąpienie `RuntimeClass` klasy.

```cpp
RuntimeClass();
```
