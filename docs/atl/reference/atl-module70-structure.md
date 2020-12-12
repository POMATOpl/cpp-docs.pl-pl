---
description: Dowiedz się więcej na temat struktury _ATL_MODULE70
title: Struktura _ATL_MODULE70
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: 8a3076cebe7cab2bce49f660e8198052af393024
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165358"
---
# <a name="_atl_module70-structure"></a>Struktura _ATL_MODULE70

Zawiera dane używane przez każdy moduł ATL.

## <a name="syntax"></a>Składnia

```cpp
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>Elementy członkowskie

`cbSize`<br/>
Rozmiar struktury używany do przechowywania wersji.

`m_nLockCnt`<br/>
Liczba odwołań, aby określić, jak długo moduł powinien pozostać aktywny.

`m_pTermFuncs`<br/>
Śledzi funkcje, które zostały zarejestrowane do wywołania, gdy ATL zostanie zamknięty.

`m_csStaticDataInitAndTypeInfo`<br/>
Służy do koordynowania dostępu do danych wewnętrznych w sytuacjach wielowątkowych.

## <a name="remarks"></a>Uwagi

[_ATL_MODULE](atl-typedefs.md#_atl_module) jest zdefiniowany jako element typedef elementu `_ATL_MODULE70` .

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../../atl/reference/atl-classes.md)
