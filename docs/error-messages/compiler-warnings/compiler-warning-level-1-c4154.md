---
title: "Kompilatora (poziom 1) ostrzeżenie C4154 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4154
dev_langs: C++
helpviewer_keywords: C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4568c107bab90587054310f2cd6b7aa3ce8f199
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4154"></a>Kompilator C4154 ostrzegawcze (poziom 1)
Usunięcie wyrażenia tablicowego; dostarczono konwersji do wskaźnika  
  
 Nie można użyć `delete` na tablicy, dlatego kompilator konwertuje tablicy na wskaźnik.  
  
## <a name="example"></a>Przykład  
  
```  
// C4154.cpp  
// compile with: /c /W1  
int main() {  
   int array[ 10 ];  
   delete array;   // C4154 can't delete stack object  
  
   int *parray2 = new int [10];  
   int (&array2)[10] = (int(&)[10]) parray2;  
   delete [] array2;   // C4154  
  
   // try the following line instead  
   delete [] &array2;  
}  
```