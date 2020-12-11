---
description: Dowiedz się więcej na temat punktów wejścia interfejsu COM
title: Punkty wejścia interfejsu COM
ms.date: 03/27/2019
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: 805ac906c3ccca246d1af71c689aaf768f789999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160015"
---
# <a name="com-interface-entry-points"></a>Punkty wejścia interfejsu COM

W przypadku funkcji Członkowskich interfejsu COM, użyj makra, `METHOD_PROLOGUE` Aby zachować właściwy stan globalny podczas wywoływania metod wyeksportowanego interfejsu.

Zazwyczaj funkcje składowe interfejsów zaimplementowane przez `CCmdTarget` obiekty pochodne już używają tego makra, aby zapewnić automatyczne inicjowanie `pThis` wskaźnika. Na przykład:

[!code-cpp[NVC_MFCConnectionPoints#5](codesnippet/cpp/com-interface-entry-points_1.cpp)]

Aby uzyskać dodatkowe informacje, zobacz [Uwagi techniczne 38](tn038-mfc-ole-iunknown-implementation.md) w implementacji MFC/OLE `IUnknown` .

`METHOD_PROLOGUE`Makro jest zdefiniowane jako:

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

Częścią makra związanego z zarządzaniem stanem globalnym jest:

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

W tym wyrażeniu przyjmuje się, że *m_pModuleState* jest zmienną członkowską zawierającego obiektu. Jest implementowana przez `CCmdTarget` klasę bazową i jest inicjowana do odpowiedniej wartości przez `COleObjectFactory` , po utworzeniu wystąpienia obiektu.

## <a name="see-also"></a>Zobacz też

[Zarządzanie danymi stanu modułów MFC](managing-the-state-data-of-mfc-modules.md)
