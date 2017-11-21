---
title: "Porady: przechwytywanie wyjątków w kodzie natywnym wygenerowanym w języku MSIL | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dbb17c9ed16f771f60054bcde1f8ea5145047c35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Porady: przechwytywanie wyjątków w kodzie natywnym wygenerowanym w języku MSIL
W kodzie natywnym można przechwycić natywnego wyjątku C++ z MSIL.  Można przechwytywać wyjątki środowiska CLR z `__try` i `__except`.  
  
 Aby uzyskać więcej informacji, zobacz [strukturalnych obsługi wyjątków (C/C++)](../cpp/structured-exception-handling-c-cpp.md) i [Obsługa wyjątków języka C++](../cpp/cpp-exception-handling.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład definiuje moduł o dwie funkcje, który natywnego wyjątek i innego, która zgłasza wyjątek MSIL.  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład definiuje moduł, który przechwytuje natywne i MSIL wyjątek.  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
```Output  
error  
caught an exception  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługa wyjątków](../windows/exception-handling-cpp-component-extensions.md)