---
description: 'Dowiedz się więcej na temat: Klasa ISessionPropertiesImpl'
title: ISessionPropertiesImpl — Klasa
ms.date: 11/04/2016
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- ISessionPropertiesImpl.SetProperties
- ISessionPropertiesImpl::SetProperties
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
ms.openlocfilehash: 6b20331de5419de868d6739a010eb5df1548a94e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287037"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl — Klasa

Zapewnia implementację interfejsu [ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85)) .

## <a name="syntax"></a>Składnia

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `ISessionPropertiesImpl` .

*PropClass*<br/>
Klasa właściwości, która jest określana przez użytkownika, która domyślnie ma wartość *T*.

## <a name="requirements"></a>Wymagania

**Nagłówek:** ATLDB. h

## <a name="members"></a>Elementy członkowskie

### <a name="interface-methods"></a>Metody interfejsu

| Nazwa | Opis |
|-|-|
|[GetProperties](#getproperties)|Zwraca listę właściwości w grupie właściwości sesji, które są obecnie ustawione w sesji.|
|[SetProperties](#setproperties)|Ustawia właściwości w grupie właściwości sesji.|

## <a name="remarks"></a>Uwagi

Obowiązkowy interfejs w sesjach. Ta klasa implementuje właściwości sesji przez wywołanie funkcji statycznej zdefiniowanej przez [mapę właściwości](./macros-for-ole-db-provider-templates.md#begin_propset_map). W klasie sesji należy określić mapę zestawu właściwości.

## <a name="isessionpropertiesimplgetproperties"></a><a name="getproperties"></a> ISessionPropertiesImpl:: GetProperties

Zwraca listę właściwości w `DBPROPSET_SESSION` grupie właściwości, które są obecnie ustawione w sesji.

### <a name="syntax"></a>Składnia

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Parametry

Zobacz [ISessionProperties:: GetProperties](/previous-versions/windows/desktop/ms723643(v=vs.85)) w *Kompendium OLE DB programisty*.

## <a name="isessionpropertiesimplsetproperties"></a><a name="setproperties"></a> ISessionPropertiesImpl:: SetProperties

Ustawia właściwości w `DBPROPSET_SESSION` grupie właściwości.

### <a name="syntax"></a>Składnia

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametry

Zobacz [ISessionProperties:: SetProperties](/previous-versions/windows/desktop/ms714405(v=vs.85)) w *Kompendium OLE DB programisty*.

## <a name="see-also"></a>Zobacz też

[Szablony dostawców OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
