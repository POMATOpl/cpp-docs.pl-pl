---
description: 'Dowiedz się więcej na temat: makra stanu obiektów'
title: Makra stanu obiektu
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 7aac547ac0b63a7db9ceea3b58befdea3e076f3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157909"
---
# <a name="object-status-macros"></a>Makra stanu obiektu

To makro ustawia flagi należące do kontrolek ActiveX.

|Nazwa|Opis|
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Używane w kontrolkach ActiveX ATL do ustawiania flag OLEMISC.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a> DECLARE_OLEMISC_STATUS

Używane w kontrolkach ActiveX ATL do ustawiania flag OLEMISC.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Parametry

*miscstatus*<br/>
Wszystkie odpowiednie flagi OLEMISC.

### <a name="remarks"></a>Uwagi

To makro służy do ustawiania flag OLEMISC dla kontrolki ActiveX. Aby uzyskać więcej informacji, zobacz [IOleObject:: GetMiscStatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Zobacz także

[Makra](../../atl/reference/atl-macros.md)
