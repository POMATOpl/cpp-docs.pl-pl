---
title: "C3070 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3070
dev_langs: C++
helpviewer_keywords: C3070
ms.assetid: ac88584d-40a6-4176-90f3-2371c3c935f2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7cbcfd17556c57c5a4640dfefb1095ba1da778d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3070"></a>C3070 błąd kompilatora
"właściwość": właściwość ma metodę "set"  
  
 Nie zdefiniowano metody dostępu set właściwości. Aby uzyskać więcej informacji, zobacz [właściwości](../../windows/property-cpp-component-extensions.md).  
  
 Poniższy przykład generuje C3070:  
  
```  
// C3070.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int size) {  
      m_data = gcnew array<int>(size);  
   }  
  
   property int % MyProp[int] {  
      int% get(int index) {   
         return m_data[index];   
      }  
   }  
  
   property int % MyProp2[int] {  
      int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, int % value) {}  
   }  
  
   property const int % MyProp3[int] {  
      const int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, const int % value) {}  
   }  
  
private:  
   array<int>^ m_data;  
};  
  
int main() {  
   R^ r = gcnew R(10);  
   r->MyProp[4] = 4;   // C3070  
  
   int value = 4;  
   r->MyProp2[4] = value;   // OK  
   r->MyProp3[4] = 4;   // OK  
}  
```