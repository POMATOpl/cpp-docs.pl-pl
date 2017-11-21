---
title: "C3899 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3899
dev_langs: C++
helpviewer_keywords: C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7d9d32b3063dbecde375159ad90eec5bf128d56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3899"></a>C3899 błąd kompilatora
"var": wykorzystanie wartości l elementu członkowskiego danych initonly nie jest dozwolone bezpośrednio w ramach równoległego regionu w klasie "class"  
  
 [Initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) nie można zainicjować elementu członkowskiego danych wewnątrz konstruktora, który znajduje się w tej części [równoległych](../../parallel/openmp/reference/parallel.md) regionu.  To dlatego kompilator jest wewnętrzny przeniesienie tego kodu tak, aby efektywnie nie jest już częścią konstruktora.  
  
 Aby rozwiązać, należy zainicjować członkowski danych initonly w konstruktorze, ale poza równoległego regionu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3899.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```