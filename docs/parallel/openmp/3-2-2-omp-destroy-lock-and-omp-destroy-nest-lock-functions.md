---
title: 3.2.2 funkcje omp_destroy_lock i omp_destroy_nest_lock funkcje | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19da0297844357cfbf8a0266600224bb13673b26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 Funkcje omp_destroy_lock i omp_destroy_nest_lock
Te funkcje upewnij się, że wskazywany do zmiennej blokady *blokady* nie został zainicjowany. Format jest następujący:  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Jest niezgodne do wywołań dowolnej z tych procedur z zmiennej blokady, która jest niezainicjowana lub odblokować.