---
title: "C2021 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2021
dev_langs: C++
helpviewer_keywords: C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d87775cb88579cae93e4de208b1386ab067a07b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2021"></a>C2021 błąd kompilatora
Oczekiwano wartości wykładnika, ale nie znaków  
  
 Znak używany jako wykładnik stałej zmiennoprzecinkowej nie jest prawidłową liczbą. Należy użyć wykładnik, który znajduje się w zakresie.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2021:  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## <a name="example"></a>Przykład  
 Możliwe rozwiązanie:  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```