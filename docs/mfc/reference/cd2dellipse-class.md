---
title: Klasa CD2DEllipse | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs:
- C++
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4c4a801952c6b29779c381237c291232ce2ef25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dellipse-class"></a>Klasa CD2DEllipse
Otoka dla `D2D1_ELLIPSE`.  
  
## <a name="syntax"></a>Składnia  
  
```  
class CD2DEllipse : public D2D1_ELLIPSE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
### <a name="public-constructors"></a>Konstruktory publiczne  
  
|Nazwa|Opis|  
|----------|-----------------|  
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Przeciążone. Konstruuje `CD2DEllipse` obiekt z `D2D1_ELLIPSE` obiektu.|  
  
## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia  
 `D2D1_ELLIPSE`  
  
 `CD2DEllipse`  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** afxrendertarget.h  
  
##  <a name="cd2dellipse"></a>  CD2DEllipse::CD2DEllipse  
 Tworzy obiekt CD2DEllipse z CD2DRectF obiektu.  
  
```  
CD2DEllipse(const CD2DRectF& rect);  
CD2DEllipse(const D2D1_ELLIPSE& ellipse);  
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

 
CD2DEllipse(
    const CD2DPointF& ptCenter,  
    const CD2DSizeF& sizeRadius);
```  
  
### <a name="parameters"></a>Parametry  
 `rect`  
 Prostokąt źródła  
  
 `ellipse`  
 elipsy źródła  
  
 `ptCenter`  
 Punktu centralnego elipsy.  
  
 `sizeRadius`  
 X radius i Y-radius elipsy.  
  
## <a name="see-also"></a>Zobacz też  
 [Klasy](../../mfc/reference/mfc-classes.md)
