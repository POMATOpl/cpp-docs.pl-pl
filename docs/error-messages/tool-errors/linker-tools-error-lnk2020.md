---
title: "Błąd narzędzi konsolidatora LNK2020 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2020
dev_langs: C++
helpviewer_keywords: LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 394cafe23851df5320a78a4e165a90422fc305de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2020"></a>Błąd narzędzi konsolidatora LNK2020
Nierozpoznany token 'token'  
  
 Podobnie jak niezdefiniowany błąd zewnętrzny, z tą różnicą, że odwołanie jest za pośrednictwem metadanych. W metadanych muszą być zdefiniowane wszystkie dane i funkcje.  
  
 Aby rozwiązać:  
  
-   Zdefiniuj Brak funkcję lub dane, lub  
  
-   Dołączyć plik obiektu lub biblioteki, w którym brak funkcji lub danych jest już zdefiniowany.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje LNK2020.  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## <a name="example"></a>Przykład  
 LNK2020 zostanie również wystąpić, jeśli można utworzyć zmiennej typu zarządzanego szablonu, ale nie również utworzyć wystąpienia typu.  
  
 Poniższy przykład generuje LNK2020.  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```