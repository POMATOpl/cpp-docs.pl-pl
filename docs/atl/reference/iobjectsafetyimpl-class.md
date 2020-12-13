---
description: 'Dowiedz się więcej na temat: Klasa IObjectSafetyImpl'
title: Klasa IObjectSafetyImpl
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: ac19fe24d12d7d09968b3e2d76f77741e83e1f81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139467"
---
# <a name="iobjectsafetyimpl-class"></a>Klasa IObjectSafetyImpl

Ta klasa udostępnia domyślną implementację interfejsu, `IObjectSafety` Aby umożliwić klientowi pobieranie i ustawianie poziomów bezpieczeństwa obiektu.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IObjectSafetyImpl` .

*dwSupportedSafety*<br/>
Określa obsługiwane opcje zabezpieczeń dla kontrolki. Może być jedną z następujących wartości:

- INTERFACESAFE_FOR_UNTRUSTED_CALLER interfejs identyfikowany przez parametr [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) `riid` powinien być bezpieczny dla skryptów.

- INTERFACESAFE_FOR_UNTRUSTED_DATA interfejs identyfikowany przez `SetInterfaceSafetyOptions` parametr `riid` powinien być bezpieczny dla niezaufanych danych podczas inicjowania.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IObjectSafetyImpl:: GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Pobiera opcje bezpieczeństwa obsługiwane przez obiekt, a także opcje bezpieczeństwa aktualnie ustawione dla obiektu.|
|[IObjectSafetyImpl:: SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Sprawia, że obiekt jest bezpieczny dla inicjalizacji lub tworzenia skryptów.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[IObjectSafetyImpl:: m_dwCurrentSafety](#m_dwcurrentsafety)|Przechowuje bieżący poziom bezpieczeństwa obiektu.|

## <a name="remarks"></a>Uwagi

Klasa `IObjectSafetyImpl` zawiera domyślną implementację programu `IObjectSafety` . `IObjectSafety`Interfejs pozwala klientowi na pobieranie i ustawianie poziomów bezpieczeństwa obiektu. Na przykład przeglądarka sieci Web może wywoływać, `IObjectSafety::SetInterfaceSafetyOptions` Aby zapewnić bezpieczną kontrolę w zakresie inicjalizacji lub bezpiecznego wykonywania skryptów.

Należy zauważyć, że użycie makra [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) z kategoriami składników CATID_SafeForScripting i CATID_SafeForInitializing zapewnia alternatywny sposób określania, czy składnik jest bezpieczny.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a> IObjectSafetyImpl:: GetInterfaceSafetyOptions

Pobiera opcje bezpieczeństwa obsługiwane przez obiekt, a także opcje bezpieczeństwa aktualnie ustawione dla obiektu.

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>Uwagi

Implementacja zwraca odpowiednie wartości dla dowolnego interfejsu obsługiwanego przez implementację obiektu `IUnknown::QueryInterface` .

> [!IMPORTANT]
> Każdy obiekt, który obsługuje `IObjectSafety` , jest odpowiedzialny za jego własne zabezpieczenia i wszystkie obiekty, które są przez niego delegowane. Programista musi wziąć pod uwagę problemy związane z uruchamianiem kodu w kontekście użytkownika, skrypty między lokacjami i wykonać odpowiednie sprawdzanie strefy.

Zobacz [IObjectSafety:: GetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) w Windows SDK.

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a> IObjectSafetyImpl:: m_dwCurrentSafety

Przechowuje bieżący poziom bezpieczeństwa obiektu.

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a> IObjectSafetyImpl:: SetInterfaceSafetyOptions

Sprawia, że obiekt jest bezpieczny dla inicjalizacji lub tworzenia skryptów, ustawiając element członkowski [m_dwCurrentSafety](#m_dwcurrentsafety) na odpowiednią wartość.

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>Uwagi

Implementacja zwraca E_NOINTERFACE dla dowolnego interfejsu, który nie jest obsługiwany przez implementację obiektu `IUnknown::QueryInterface` .

> [!IMPORTANT]
> Każdy obiekt, który obsługuje `IObjectSafety` , jest odpowiedzialny za jego własne zabezpieczenia i wszystkie obiekty, które są przez niego delegowane. Programista musi wziąć pod uwagę problemy związane z uruchamianiem kodu w kontekście użytkownika, skrypty między lokacjami i wykonać odpowiednie sprawdzanie strefy.

Zobacz [IObjectSafety:: SetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[IObjectSafety, interfejs](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
