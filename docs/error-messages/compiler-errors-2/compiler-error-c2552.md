---
title: "C2552 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2552
dev_langs:
- C++
helpviewer_keywords:
- C2552
ms.assetid: 0e0ab759-788a-4faf-9337-80d4b9e2e8c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a438d602c23d15a1196fe4d40a5cca98867828
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2552"></a>C2552 błąd kompilatora
„identyfikator”: obiektów niebędących agregacjami nie można zainicjować z listy inicjatorów  
  
 Identyfikator agregacji został niepoprawnie zainicjowany.  
  
 [Agreguje](../../c-language/initializing-aggregate-types.md) są zdefiniowane jako:  
  
-   Tablice  
  
-   Klasy, struktury i złożenia, które nie mają:  
  
    -   Konstruktorów  
  
    -   Składników prywatnych ani chronionych  
  
    -   Klas podstawowych  
  
    -   Funkcji wirtualnych  
  
 Ponadto, program Visual C++ nie zezwala na typy danych w agregacji, która zawiera konstruktory.  
  
 Poniżej przedstawiono możliwe przyczyny wygenerowania błędu C2552 w reakcji na próbę zainicjowania agregacji wobec typu:  
  
-   Typ ma co najmniej jednego konstruktora zdefiniowanego przez użytkownika.  
  
-   Typ ma co najmniej jeden niestatyczny, prywatny element członkowski danych.  
  
-   Typ ma co najmniej jedną funkcję wirtualną.  
  
-   Typ ma klasę bazową.  
  
-   Typ jest klasą ref lub interfejsem CLR.  
  
-   Typ ma tablicę o nieustalonym wymiarze (tablicę zerową), której elementy mają destruktory.  
  
 Poniższy przykład spowoduje wygenerowanie błędu C2552:  
  
```  
// C2552.cpp  
// compile with: /clr  
#include <string>  
using namespace std;  
  
struct Pair_Incorrect {  
private:  
   string m_name;  
   double m_val;  
};  
  
struct Pair_Correct1 {  
public:  
   Pair_Correct1(string name, double val)  
      : m_name(name), m_val(val) {}  
  
private:  
   string m_name;  
   double m_val;  
};  
  
struct Pair_Correct2 {  
public:  
   string m_name;  
   double m_val;  
};  
  
int main() {  
   // To fix, add a constructor to this class and use it for   
   // initializing the data members, see Pair_Correct1 (below)  
   // or  
   // Do not have any private or protected non-static data members,   
   // see Pair_Correct2 (below).  Pair_Correct2 is not recommended in   
   // case your object model requires some non-static data members to   
   // be private or protected  
  
   string name("John");  
   Pair_Incorrect pair1 = { name, 0.0 };   // C2552  
  
   // initialize a CLR immutable value type that has a constructor  
   System::DateTime dt = {2001, 4, 12, 22, 16, 49, 844};   // C2552   
  
   Pair_Correct1 pair2( name, 0.0 );  
   Pair_Correct1 pair3 = Pair_Correct1( name, 0.0 );  
   Pair_Correct2 pair4 = { name, 0.0 };  
   System::DateTime dt2(2001, 4, 12, 22, 16, 49, 844);  
}  
```