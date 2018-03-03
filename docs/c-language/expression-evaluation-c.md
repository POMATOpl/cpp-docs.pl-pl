---
title: "Wyrażenie Evaluation (C) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9984444bd7de3144cb1e81ddb527c68531a9d7d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluation-c"></a>Szacowanie wyrażeń (C)
Wyrażeń zawierających przypisania, przyrost jednoargumentowe, dekrementacja jednoargumentowy lub wywołanie funkcji może mieć skutki uboczne ich oceny (efekty uboczne). Po osiągnięciu "punktu sekwencji" wszystko poprzedzających punktu sekwencji, w tym żadnych efektów ubocznych, jest gwarantowane zostało obliczone przed rozpoczęciem oceny na niczego następującego punktu sekwencji.  
  
 "Efekty uboczne" modyfikacje spowodowane przez ocenę wyrażenia. Efekty uboczne występuje po zmianie wartości zmiennej przez Obliczanie wyrażenia. Wszystkie operacje przypisania mieć skutki uboczne. Wywołania funkcji również może mieć efekty uboczne, ich zmiany wartości elementu widoczne na zewnątrz przypisania bezpośredniego lub pośredniego przypisania za pomocą wskaźnika.  
  
## <a name="see-also"></a>Zobacz też  
 [Operandy i wyrażenia](../c-language/operands-and-expressions.md)