---
title: "C3459 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3459
dev_langs: C++
helpviewer_keywords: C3459
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 703844f749ea2911d2472079053608474de56785
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3459"></a>C3459 błąd kompilatora
"attribute": atrybut dozwolone tylko w indeksatorze klasy (Właściwość indeksowana domyślnie)  
  
Atrybut, który jest przeznaczony do zastosowania dla właściwości indeksatora klasy zostało niepoprawnie użyte.  
  
Aby uzyskać więcej informacji, zobacz [porady: użycie właściwości w języku C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).  
  
## <a name="example"></a>Przykład  
Poniższy przykład generuje C3459.  
  
```  
// C3459.cpp  
// compile with: /clr /c  
public ref class MyString {  
public:  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459  
   property int Prop;  
};  
  
// OK  
public ref class MyString2 {  
   array<int>^ MyArr;  
public:  
   MyString2() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
```