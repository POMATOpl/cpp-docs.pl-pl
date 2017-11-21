---
title: "Instrukcja wyrażeń | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 80493922076514ce254d01a97dd0c86f51c92ac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
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