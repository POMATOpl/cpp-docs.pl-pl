---
title: "Instrukcja wyrażeń | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e627e107df850f31a9cf04981795edd1185c0ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="expression-statement"></a>Instrukcja wyrażeń
Instrukcje wyrażeń spowodować wyrażenia do obliczenia. Transfer nie formant lub iteracji odbywa się w wyniku wyrażenia instrukcji.  
  
 Składnia instrukcji wyrażenia jest po prostu  
  
## <a name="syntax"></a>Składnia  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Uwagi  
 Wszystkie wyrażenia w instrukcji wyrażenia są oceniane i wykonywane są wszystkie efekty uboczne, przed wykonaniem następnej instrukcji. Najbardziej typowe instrukcje wyrażenia są zadania i wywołania funkcji.  Ponieważ wyrażenie jest opcjonalne, tylko średnik jest uznawany za instrukcji puste wyrażenie określone jako [null](../cpp/null-statement.md) instrukcji.  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd instrukcji C++](../cpp/overview-of-cpp-statements.md)