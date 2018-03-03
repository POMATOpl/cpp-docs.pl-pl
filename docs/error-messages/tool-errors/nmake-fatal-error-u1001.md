---
title: "Błąd krytyczny NMAKE U1001 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1001
dev_langs:
- C++
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c4a9285e5092f0e846e78457e440db55d84d51e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1001"></a>Błąd krytyczny NMAKE U1001
Błąd składni: niedozwolony znak "character" w makrze  
  
 Podany znak pojawia się w makrze, ale nie jest literą, cyfrą lub podkreślenia.  
  
 Przyczyną tego błędu może być brak dwukropka w rozwinięciu makra:  
  
```  
syntax error : illegal character '=' in macro  
```