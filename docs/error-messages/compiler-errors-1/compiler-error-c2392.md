---
title: "C2392 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2392
dev_langs: C++
helpviewer_keywords: C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6fa5164028a622b03eb770e24a91c4b07968c3bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2392"></a>C2392 błąd kompilatora
"metoda1": kowariantne wyniki zwracane typy nie są obsługiwane w zarządzanych lub WinRTtypes, w przeciwnym razie metoda2 zostanie przesłonięte  
  
 Kowariantne typy zwracane są niedozwolone dla funkcji Członkowskich środowiska wykonawczego systemu Windows lub podczas kompilowania za pomocą [/CLR (kompilacja języka wspólnego środowiska uruchomieniowego)](../../build/reference/clr-common-language-runtime-compilation.md) opcji.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2392 i pokazuje, jak go naprawić.  
  
```  
// C2392.cpp  
// compile with: /clr  
public ref struct B {  
public:  
   int i;  
};  
  
public ref struct D: public B{};  
  
public ref struct B1 {  
public:  
   virtual B^ mf() {  
      B^ pB = gcnew B;  
      pB->i = 11;  
      return pB;  
   }  
};  
  
public ref struct D1: public B1 {  
public:  
   virtual D^ mf() override {  // C2392  
   // try the following line instead  
   // virtual B^ mf() override {  
   // return type D^ is covariant with B^, not allowed with CLR types  
      D^ pD = gcnew D;  
      pD->i = 12;  
      return pD;  
   }  
};  
  
int main() {  
   B1^ pB1 = gcnew D1;  
   B^ pB = pB1->mf();  
   D^ pD = dynamic_cast<D^>(pB);  
}  
```