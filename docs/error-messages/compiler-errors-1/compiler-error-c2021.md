---
title: C2021 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae1c3640b4fbe5b1473c2e678406321f5533e586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
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