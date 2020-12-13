---
description: Dowiedz się więcej o interfejsie IRegistrar
title: IRegistrar, interfejs
ms.date: 02/01/2017
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
ms.openlocfilehash: 9a138468ccbf21594c4e9d88d1ed2387a4c1052a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139168"
---
# <a name="iregistrar-interface"></a>IRegistrar, interfejs

Ten interfejs jest zdefiniowany w atliface. h i jest używany wewnętrznie przez CAtlModule funkcje członkowskie, takie jak [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced).

## <a name="syntax"></a>Składnia

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz temat [Używanie parametrów wymiennych (preprocesora rejestratora)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Rejestruje zasób. |
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| Wyrejestrowuje zasób.|
|[IRegistrar::FileRegister](#fileregister)|Rejestruje plik.|
|[IRegistrar::FileUnregister](#fileunregister)|Wyrejestrowuje plik.|
|[IRegistrar::StringRegister](#stringregister)|Rejestruje ciąg.|
|[IRegistrar::StringUnregister](#stringunregister)|Wyrejestrowuje ciąg|
|[IRegistrar::ResourceRegister](#resourceregister)|Rejestruje zasób.|
|[IRegistrar::ResourceUnregister](#resourceunregister)|Wyrejestrowuje zasób.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlifase. h

## <a name="iregistrarresourceregistersz"></a><a name="resourceregistersz"></a> IRegistrar::ResourceRegisterSz

Rejestruje zasób.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a> IRegistrar::ResourceUnregisterSz

Wyrejestrowuje zasób.

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarfileregister"></a><a name="fileregister"></a> IRegistrar::FileRegister

Rejestruje plik.

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarfileunregister"></a><a name="fileunregister"></a> IRegistrar::FileUnregister

Wyrejestrowuje plik.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarstringregister"></a><a name="stringregister"></a> IRegistrar::StringRegister

Rejestruje określone dane ciągu.

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarstringunregister"></a><a name="stringunregister"></a> IRegistrar::StringUnregister

Wyrejestrowuje określone dane ciągu.

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarresourceregister"></a><a name="resourceregister"></a> IRegistrar::ResourceRegister

Rejestruje zasób.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregister"></a><a name="resourceunregister"></a> IRegistrar::ResourceUnregister

Wyrejestrowuje zasób.

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>Zobacz też

[Używanie parametrów wymiennych (preprocesora rejestratora)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasy modułów](../../atl/atl-module-classes.md)<br/>
[Składnik rejestru (Rejestrator)](../../atl/atl-registry-component-registrar.md)
