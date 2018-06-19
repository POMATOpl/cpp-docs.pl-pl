---
title: C2057 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2057
dev_langs:
- C++
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a48598fba0e27aa875ec5ec2a97aaa4ef9d5326
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168233"
---
# <a name="compiler-error-c2057"></a>C2057 błąd kompilatora
Oczekiwano wyrażenia stałego  
  
 Kontekst wymaga wyrażenie stałe wyrażenie, którego wartość jest znany w czasie kompilacji.  
  
 Kompilator musi znać rozmiar typu w czasie kompilacji, aby przydzielić miejsce dla wystąpienia tego typu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2057 i pokazuje, jak rozwiązywanie problemu:  
  
```  
// C2057.cpp  
int i;  
int b[i];   // C2057 - value of i is unknown at compile time  
int main() {  
   const int i = 8;  
   int b[i]; // OK - value of i is fixed and known to compiler  
}  
```  
  
## <a name="example"></a>Przykład  
 C o bardziej restrykcyjne zasady wyrażenia stałe.  Poniższy przykład generuje C2057 i pokazuje, jak rozwiązywanie problemu:  
  
```  
// C2057b.c  
#define ArraySize1 10  
int main() {   
   const int ArraySize2 = 10;   
   int h[ArraySize2];   // C2057 - C does not allow variables here  
   int h[ArraySize1];   // OK - uses preprocessor constant  
}  
```