---
description: 'Dowiedz się więcej na temat: Klasa IRunnableObjectImpl'
title: Klasa IRunnableObjectImpl
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: ecae31d23eb68ce45e9b140a3e5034fb6c5400fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158117"
---
# <a name="irunnableobjectimpl-class"></a>Klasa IRunnableObjectImpl

Ta klasa implementuje `IUnknown` i udostępnia domyślną implementację interfejsu [IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IRunnableObjectImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Zwraca identyfikator CLSID uruchomionej kontrolki. Implementacja ATL ustawia identyfikator CLSID GUID_NULL i zwraca E_UNEXPECTED.|
|[IRunnableObjectImpl:: IsRunning](#isrunning)|Określa, czy kontrolka jest uruchomiona. Implementacja ATL zwraca wartość TRUE.|
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Blokuje formant w stanie uruchomienia. Implementacja ATL zwraca S_OK.|
|[IRunnableObjectImpl:: Run](#run)|Wymusza uruchomienie formantu. Implementacja ATL zwraca S_OK.|
|[IRunnableObjectImpl:: setzawierałobject](#setcontainedobject)|Wskazuje, że formant jest osadzony. Implementacja ATL zwraca S_OK.|

## <a name="remarks"></a>Uwagi

Interfejs [IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) umożliwia kontenerowi określenie, czy kontrolka jest uruchomiona, wymuszenie jej uruchomienia lub zablokowanie jej w stanie uruchomionym. Klasa `IRunnableObjectImpl` zapewnia domyślną implementację tego interfejsu i implementuje `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a> IRunnableObjectImpl::GetRunningClass

Zwraca identyfikator CLSID uruchomionej kontrolki.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>Wartość zwracana

Implementacja ATL ustawia \* *lpClsid* do GUID_NULL i zwraca E_UNEXPECTED.

### <a name="remarks"></a>Uwagi

Zobacz [IRunnableObject:: GetRunningClass](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) w Windows SDK.

## <a name="irunnableobjectimplisrunning"></a><a name="isrunning"></a> IRunnableObjectImpl:: IsRunning

Określa, czy kontrolka jest uruchomiona.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Wartość zwracana

Implementacja ATL zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Zobacz [IRunnableObject:: Isdziałanie](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) w Windows SDK.

## <a name="irunnableobjectimpllockrunning"></a><a name="lockrunning"></a> IRunnableObjectImpl::LockRunning

Blokuje formant w stanie uruchomienia.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Wartość zwracana

Implementacja ATL zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IRunnableObject:: LockRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) w Windows SDK.

## <a name="irunnableobjectimplrun"></a><a name="run"></a> IRunnableObjectImpl:: Run

Wymusza uruchomienie formantu.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Wartość zwracana

Implementacja ATL zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IRunnableObject:: Run](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) w Windows SDK.

## <a name="irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a> IRunnableObjectImpl:: setzawierałobject

Wskazuje, że formant jest osadzony.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Wartość zwracana

Implementacja ATL zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IRunnableObject:: Setzawierałobject](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
