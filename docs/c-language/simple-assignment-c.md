---
title: Proste Assignment (C) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c6f81732b4fccdac6ae0912b7617c28318da3e55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="simple-assignment-c"></a>Przypisanie proste (C)
Operator przypisania prostego przypisuje jej prawy operand operand po lewej stronie. Wartość prawy operand jest konwertowana na typ wyrażenia przypisania i zastępuje do wartości przechowywanej w obiekcie wskazywany przez argument po lewej stronie. Zastosuj reguły konwersji dla przypisania (zobacz [konwersje przypisań](../c-language/assignment-conversions.md)).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 W tym przykładzie wartość `y` jest konwertowana na typ **podwójne** i przypisane do `x`.  
  
## <a name="see-also"></a>Zobacz też  
 [Operatory przypisania w języku C](../c-language/c-assignment-operators.md)