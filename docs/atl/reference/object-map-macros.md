---
description: 'Dowiedz się więcej na temat: makra mapy obiektów'
title: Makra mapy obiektów
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: accd1fdaebaab3a5c71730dcfd5db83fc2b320de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139038"
---
# <a name="object-map-macros"></a>Makra mapy obiektów

Te makra definiują mapowania obiektów i wpisy.

|Nazwa|Opis|
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Umożliwia określenie opisu tekstu obiektu klasy, który zostanie wprowadzony do mapy obiektu.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Wprowadza obiekt ATL do mapy obiektów, aktualizuje rejestr i tworzy wystąpienie obiektu.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Pozwala określić, że obiekt powinien być zarejestrowany i zainicjowany, ale nie powinien być zewnętrznym możliwym do utworzenia za pośrednictwem `CoCreateInstance` .|

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="declare_object_description"></a><a name="declare_object_description"></a> DECLARE_OBJECT_DESCRIPTION

Umożliwia określenie tekstu opisu obiektu klasy.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Parametry

*x*<br/>
podczas Opis obiektu klasy.

### <a name="remarks"></a>Uwagi

ATL wprowadza ten opis do mapowania obiektu za pomocą makra [OBJECT_ENTRY_AUTO](#object_entry_auto) .

DECLARE_OBJECT_DESCRIPTION implementuje `GetObjectDescription` funkcję, której można użyć, aby przesłonić metodę [CComCoClass:: GetObjectDescription](ccomcoclass-class.md#getobjectdescription) .

`GetObjectDescription`Funkcja jest wywoływana przez `IComponentRegistrar::GetComponents` . `IComponentRegistrar` jest interfejsem automatyzacji, który umożliwia rejestrowanie i Wyrejestrowywanie poszczególnych składników w bibliotece DLL. Podczas tworzenia obiektu rejestratora składników przy użyciu Kreatora projektu ATL Kreator automatycznie implementuje `IComponentRegistrar` interfejs. `IComponentRegistrar` jest zwykle używany przez program Microsoft Transaction Server.

Aby uzyskać więcej informacji na temat Kreatora projektu ATL, zobacz artykuł [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

## <a name="object_entry_auto"></a><a name="object_entry_auto"></a> OBJECT_ENTRY_AUTO

Wprowadza obiekt ATL do mapy obiektów, aktualizuje rejestr i tworzy wystąpienie obiektu.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametry

*Identyfikator*<br/>
podczas Identyfikator CLSID klasy COM zaimplementowanej przez klasę C++ o nazwie *Class*.

*określonej*<br/>
podczas Nazwa klasy języka C++ implementująca klasę COM reprezentowaną przez *CLSID*.

### <a name="remarks"></a>Uwagi

Makra wpisów obiektów są umieszczane w zakresie globalnym w projekcie w celu zapewnienia obsługi rejestracji, inicjalizacji i tworzenia klasy.

OBJECT_ENTRY_AUTO wprowadza do wskaźników funkcji klasy twórcy i funkcji klasy twórcy fabryki `CreateInstance` dla tego obiektu do automatycznie generowanej mapy obiektów ATL. Gdy wywoływana jest [CAtlComModule:: RegisterServer](catlcommodule-class.md#registerserver) , aktualizuje rejestr systemu dla każdego obiektu na mapie obiektów.

W poniższej tabeli opisano, jak informacje dodawane do mapy obiektów są uzyskiwane z klasy podanej jako drugi parametr tego makra.

|Informacje dla|Uzyskane z|
|---------------------|-------------------|
|Rejestracja COM|[Makra rejestru](../../atl/reference/registry-macros.md)|
|Tworzenie fabryki klas|[Makra fabryki klas](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Tworzenie wystąpienia|[Makra agregacji](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Rejestracja kategorii składników|[Makra kategorii](../../atl/reference/category-macros.md)|
|Inicjowanie i oczyszczanie na poziomie klasy|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

## <a name="object_entry_non_createable_ex_auto"></a><a name="object_entry_non_createable_ex_auto"></a> OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Pozwala określić, że obiekt powinien być zarejestrowany i zainicjowany, ale nie powinien być zewnętrznym możliwym do utworzenia za pośrednictwem `CoCreateInstance` .

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametry

*Identyfikator*<br/>
podczas Identyfikator CLSID klasy COM zaimplementowanej przez klasę C++ o nazwie *Class*.

*określonej*<br/>
podczas Nazwa klasy języka C++ implementująca klasę COM reprezentowaną przez *CLSID*.

### <a name="remarks"></a>Uwagi

Makra wpisów obiektów są umieszczane w zakresie globalnym w projekcie w celu zapewnienia obsługi rejestracji, inicjalizacji i tworzenia klasy.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO pozwala określić, że obiekt powinien być zarejestrowany i zainicjowany (zobacz [OBJECT_ENTRY_AUTO](#object_entry_auto) , aby uzyskać więcej informacji), ale nie powinien być możliwy do utworzenia za pośrednictwem `CoCreateInstance` .

## <a name="see-also"></a>Zobacz też

[Makra](../../atl/reference/atl-macros.md)
