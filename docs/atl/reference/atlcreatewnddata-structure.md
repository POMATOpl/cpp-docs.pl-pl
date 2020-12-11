---
description: Dowiedz się więcej na temat struktury _AtlCreateWndData
title: Struktura _AtlCreateWndData
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: 912f2d108baa9cae1b91a34f3c5e386339d11f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158611"
---
# <a name="_atlcreatewnddata-structure"></a>Struktura _AtlCreateWndData

Ta struktura zawiera dane wystąpienia klasy w kodzie systemu Windows w ATL.

## <a name="syntax"></a>Składnia

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Elementy członkowskie

`m_pThis`<br/>
**`this`** Wskaźnik używany do uzyskania dostępu do wystąpienia klasy w procedurach okna.

`m_dwThreadID`<br/>
Identyfikator wątku bieżącego wystąpienia klasy.

`m_pNext`<br/>
Wskaźnik do następnego `_AtlCreateWndData` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../../atl/reference/atl-classes.md)
