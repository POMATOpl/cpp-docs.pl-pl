---
title: 2.7.2.4 udostępnione | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1de0e32e16d889acb8f1339d783bc194b3508dda
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="2724-shared"></a>2.7.2.4 — udostępnione
Klauzulę udostępnia zmienne, które są widoczne w *zmiennej listy* wśród wszystkich wątków w zespole. Wszystkie wątki w zespole dostęp do tego samego obszaru magazynu dla **udostępnionego** zmiennych.  
  
 Składnia **udostępnionego** klauzuli wygląda następująco:  
  
```  
shared(variable-list)  
```