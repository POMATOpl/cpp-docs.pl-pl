---
title: "Zmienne zakresu A.21 z klauzulą prywatnej | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 761141b1f71758bb751fbcb29f2c9b395279e174
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="a21---scoping-variables-with-the-private-clause"></a>A.21   Zmienne zakresowe z klauzulą prywatną
Wartości `i` i `j` w poniższym przykładzie zdefiniowano przy zamykaniu od równoległego regionu:  
  
```  
int i, j;  
i = 1;  
j = 2;  
#pragma omp parallel private(i) firstprivate(j)  
{  
  i = 3;  
  j = j + 2;  
}  
printf_s("%d %d\n", i, j);  
```  
  
 Aby uzyskać więcej informacji na temat `private` klauzuli, zobacz [sekcji 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) na stronie 25.