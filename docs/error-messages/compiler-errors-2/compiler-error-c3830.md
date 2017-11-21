---
title: "C3830 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3830
dev_langs: C++
helpviewer_keywords: C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2f821b1ba6dc523ba3a664fb9c8b658dee1c78f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3830"></a>C3830 błąd kompilatora
"type1": nie może dziedziczyć po "type2", wartość typów może dziedziczyć tylko z klas interfejsów  
  
 Typ wartości nie może dziedziczyć klasy podstawowej.  Aby uzyskać więcej informacji, zobacz [klas i struktur](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3830:  
  
```  
// C3830a.cpp  
// compile with: /clr /c  
public value struct MyStruct4 {  
   int i;  
};  
  
public value class MyClass : public MyStruct4 {};   // C3830  
  
// OK  
public interface struct MyInterface4 {  
   void i();  
};  
  
public value class MyClass2 : public MyInterface4 {  
public:  
   virtual void i(){}  
};  
```  
