---
title: "Porady: iterowanie przez tablice za pomocą instrukcji for each | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], iterating with for each
ms.assetid: ddc88ce2-69e1-44fc-af84-5b6f62fcb9e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 437e9134e489d9ca91f95979ad5165798d90cdef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-iterate-over-arrays-with-for-each"></a>Porady: iterowanie przez tablice za pomocą instrukcji for each
W tym temacie przedstawiono sposób użycia [dla poszczególnych usług, w](../dotnet/for-each-in.md) — słowo kluczowe w różnych typów tablic.  
  
## <a name="example"></a>Przykład  
 Ten przykład przedstawia sposób użycia `for each` na tablicę typów referencyjnych.  Należy pamiętać, że jeśli wymiarów dla wielu wymiarów tablicy wynosi zero, `for each` za pośrednictwem tablicy nie iteracji pętli.  
  
```  
// for_each_arrays.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyClass {  
   void Test() { Console::WriteLine("in MyClass"); }  
};  
  
ref struct MyClass2 {  
   void Test() { Console::WriteLine("in MyClass2"); }  
};  
  
int main() {  
   array<MyClass ^> ^ MyArray = gcnew array<MyClass ^>(2);  
  
   int i = 0;  
   for each ( MyClass ^ c in MyArray ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
  
   Console::WriteLine();  
  
   array< MyClass2 ^, 2 > ^ MyArray2 = gcnew array< MyClass2 ^, 2 >(2, 2);  
   i = 0;  
   for each ( MyClass2 ^ c in MyArray2 ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
  
   array< MyClass2 ^, 2 > ^ MyArray3 = gcnew array< MyClass2 ^, 2 >(2, 0);  
   i = 0;  
   for each ( MyClass2 ^ c in MyArray3 ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
}  
```  
  
```Output  
0 = in MyClass  
1 = in MyClass  
  
0 = in MyClass2  
1 = in MyClass2  
2 = in MyClass2  
3 = in MyClass2  
```  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano dla każdego Iterowanie po <xref:System.Collections.ArrayList>, który implementuje <xref:System.Collections.IEnumerable>.  
  
```  
// for_each_arrays_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
  
int main() {  
   int retval = 0;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(10);  
   arr->Add(20);  
   arr->Add(30);  
  
   for each ( int c in arr )  
      retval += c;  
   Console::WriteLine(retval);  
}  
```  
  
```Output  
60  
```  
  
## <a name="example"></a>Przykład  
 Ten przykład przedstawia sposób iteracja tablicy tablic.  
  
```  
// for_each_arrays_3.cpp  
// compile with: /clr  
using namespace System;  
  
#define ARRAY_SIZE 2  
  
int main() {  
   int i, j;  
  
   // Declares an array of managed arrays of Int32.  
   array< array< Int32 > ^ > ^ IntArray = gcnew array<array< Int32 > ^>(ARRAY_SIZE);  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++) {  
      IntArray[i] = gcnew array< Int32 >(ARRAY_SIZE);  
         for ( int j = 0 ; j < ARRAY_SIZE ; j++ )   
            IntArray[i][j] = i + 10;  
   }  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++)  
      for (int j = 0 ; j < ARRAY_SIZE ; j++)  
         Console::WriteLine("IntArray[{0}] = {1}", i, IntArray[i][j]);  
   Console::WriteLine();  
  
   for each (array<Int32> ^ xyz in IntArray)  
      for each ( int c in xyz )  
         Console::WriteLine(c);  
}  
```  
  
```Output  
IntArray[0] = 10  
IntArray[0] = 10  
IntArray[1] = 11  
IntArray[1] = 11  
  
10  
10  
11  
11  
```  
  
## <a name="see-also"></a>Zobacz też  
 [for each, in](../dotnet/for-each-in.md)