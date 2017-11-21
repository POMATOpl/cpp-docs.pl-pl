---
title: "Przykład punktu połączenia ATL | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 518976381209fe774f32b286e42a9840159a9404
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="atl-connection-point-example"></a>Przykład punktu połączenia ATL
W tym przykładzie pokazano obiekt, który obsługuje [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) jako interfejs wychodzących:  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]  
  
 Podczas określania `IPropertyNotifySink` jako interfejs wychodzących, można użyć klasy [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) zamiast `IConnectionPointImpl`. Na przykład:  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]  
  
## <a name="see-also"></a>Zobacz też  
 [Punkt połączenia](../atl/atl-connection-points.md)

