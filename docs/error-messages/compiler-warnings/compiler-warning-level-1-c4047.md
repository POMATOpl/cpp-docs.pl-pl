---
title: Kompilatora (poziom 1) ostrzeżenie C4047 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4047
dev_langs:
- C++
helpviewer_keywords:
- C4047
ms.assetid: b75ad6fb-5c93-4434-a85f-c4083051a5de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fe176c0f56f7d3115879efcef2b9689df6152a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4047"></a>Kompilator C4047 ostrzegawcze (poziom 1)
"operator": "identifier1" różni się w poziomach pośredników od "identifier2"  
  
 Wskaźnik może wskazywać zmiennej (jeden poziom pośredni), do innego wskaźnika wskazujące zmiennej (dwa poziomy pośredni) i tak dalej.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4047:  
  
```  
// C4047.c  
// compile with: /W1  
  
int main() {  
   char **p = 0;   // two levels of indirection  
   char *q = 0;   // one level of indirection  
  
   char *p2 = 0;   // one level of indirection  
   char *q2 = 0;   // one level of indirection  
  
   p = q;   // C4047  
   p2 = q2;  
}  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4047:  
  
```  
// C4047b.c  
// compile with: /W1  
#include <stdio.h>  
  
int main() {  
   int i;  
   FILE *myFile = NULL;  
   errno_t  err = 0;  
   char file_name[256];  
   char *cs = 0;  
  
   err = fopen_s(&myFile, "C4047.txt", "r");  
   if ((err != 0) || (myFile)) {  
      printf_s("fopen_s failed!\n");  
      exit(-1);  
    }  
   i = fgets(file_name, 256, myFile);   // C4047  
   cs = fgets(file_name, 256, myFile);   // OK  
}  
```