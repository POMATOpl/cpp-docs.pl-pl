---
title: RECT Structure1 | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f4e56c78e717b24390a82e7cbb55670f36369044
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="rect-structure1"></a>RECT Structure1
`RECT` Struktury definiuje współrzędne górnego lewego i prawego dolnego rogu prostokąta.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>Elementy członkowskie  
 `left`  
 Określa współrzędną x górnego lewego rogu prostokąta.  
  
 `top`  
 Określa współrzędną y górnego lewego rogu prostokąta.  
  
 `right`  
 Określa współrzędną x prawym dolnym rogu prostokąta.  
  
 `bottom`  
 Określa współrzędną y prawego dolnego rogu prostokąta.  
  
## <a name="example"></a>Przykład  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** windef.h  
  
## <a name="see-also"></a>Zobacz też  
 [Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect, klasa](../../atl-mfc-shared/reference/crect-class.md)
