---
description: Dowiedz się więcej na temat struktury _ATL_COM_MODULE70
title: Struktura _ATL_COM_MODULE70
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: db2139d1c816c13e6da104f6a6d785ef35a07721
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165411"
---
# <a name="_atl_com_module70-structure"></a>Struktura _ATL_COM_MODULE70

Używany przez kod związany z modelem COM w ATL.

## <a name="syntax"></a>Składnia

```cpp
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>Elementy członkowskie

`cbSize`<br/>
Rozmiar struktury używany do przechowywania wersji.

`m_hInstTypeLib`<br/>
Wystąpienie uchwytu do biblioteki typów dla tego modułu.

`m_ppAutoObjMapFirst`<br/>
Adres elementu tablicy wskazujący początek wpisów mapowania obiektów dla tego modułu.

`m_ppAutoObjMapLast`<br/>
Adres elementu tablicy wskazujący koniec wpisów mapowania obiektów dla tego modułu.

`m_csObjMap`<br/>
Sekcja krytyczna do serializacji dostępu do wpisów mapowania obiektów. Używane wewnętrznie przez ATL.

## <a name="remarks"></a>Uwagi

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) jest zdefiniowany jako element typedef _ATL_COM_MODULE70.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../../atl/reference/atl-classes.md)
