---
description: 'Dowiedz się więcej na temat: Klasa CComQIPtr'
title: Klasa CComQIPtr
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: e5af938cd7b2bbae3b091eac5323d3455ce1cf02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142327"
---
# <a name="ccomqiptr-class"></a>Klasa CComQIPtr

Klasa inteligentnego wskaźnika do zarządzania wskaźnikami interfejsu COM.

## <a name="syntax"></a>Składnia

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Interfejs COM określający typ wskaźnika, który ma być przechowywany.

*piid*<br/>
Wskaźnik do IID elementu *T*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComQIPtr:: CComQIPtr](#ccomqiptr)|Konstruktor.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComQIPtr:: operator =](#operator_eq)|Przypisuje wskaźnik do wskaźnika elementu członkowskiego.|

## <a name="remarks"></a>Uwagi

ATL używa `CComQIPtr` i [CComPtr](../../atl/reference/ccomptr-class.md) do zarządzania wskaźnikami interfejsu com, z których oba pochodzą z [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Obie klasy wykonują automatyczne zliczanie odwołań poprzez wywołania do `AddRef` i `Release` . Przeciążone operatory obsługują operacje wskaźnika.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcomcli. h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a> CComQIPtr:: CComQIPtr

Konstruktor.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>Parametry

*LP*<br/>
Służy do inicjowania wskaźnika interfejsu.

*T*<br/>
Interfejs COM.

*piid*<br/>
Wskaźnik do IID elementu *T*.

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a> CComQIPtr:: operator =

Operator przypisania.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>Parametry

*LP*<br/>
Służy do inicjowania wskaźnika interfejsu.

*T*<br/>
Interfejs COM.

*piid*<br/>
Wskaźnik do IID elementu *T*.

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do zaktualizowanego `CComQIPtr` obiektu.

## <a name="see-also"></a>Zobacz też

[CComPtr:: CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](#ccomqiptr)<br/>
[Klasa CComPtrBase](../../atl/reference/ccomptrbase-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasa CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)
