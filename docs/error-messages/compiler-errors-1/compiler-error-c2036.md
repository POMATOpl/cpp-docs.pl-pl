---
title: "C2036 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2036
dev_langs: C++
helpviewer_keywords: C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8ffb8f2b8ad0df1741687c1081fc499d3a9fde31
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2036"></a>C2036 błąd kompilatora
'Identyfikator': nieznany rozmiar  
  
 Operacja na `identifier` wymaga podania rozmiaru obiektu danych, który nie może być określony.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2036.  
  
```  
// C2036.c  
// a C program  
struct A* pA;  
struct B { int i; } *pB;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*)pA)++;   // OK  
  
   pB++;   // OK  
}  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2036.  
  
```  
// C2036_2.cpp  
// a C++ program  
struct A* pA;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)  
}  
```