---
title: Błąd krytyczny C1026 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24c034d45b7f8b222471094f4580902ae1b8dc66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1026"></a>Błąd krytyczny C1026
przepełnienie stosu analizatora składni, zbyt złożony program  
  
 Miejsce wymagane do analizy programu spowodowała przepełnienie stosu kompilatora.  
  
 Zmniejsz stopień złożoności wyrażeń przez:  
  
-   Zmniejszenie zagnieżdżenia w `for` i `switch` instrukcje. Umieść głębsze zagnieżdżonych instrukcji w osobnych funkcji.  
  
-   Podzielenie dużo wyrażeń, które wymagają operatory przecinkami lub wywołania funkcji.