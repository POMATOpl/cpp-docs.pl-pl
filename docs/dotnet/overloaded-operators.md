---
title: "Przeciążone operatory | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operator overloading, in a CLR class
- operators [C++], overloading
ms.assetid: 30391426-afe7-4497-bf22-e4816c1e48c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 94ee9d7bcffe7d17a5d5cf91fa3accdbe206b641
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="overloaded-operators"></a>Operatory przeciążone
Przeładowanie operatora zmienił się znacznie z rozszerzeń zarządzanych dla języka C++ dla Visual C++.  
  
 W deklaracji typu referencyjnego, na przykład zamiast za pomocą natywnego `operator+` składni, musisz jawnie zapisać wewnętrzna nazwa podstawowej operator — w takim przypadku `op_Addition`. Ponadto wywołanie operator ma jawnie wywoływanej za pomocą tej samej nazwie, w związku z tym ograniczenia dwie główne korzyści wynikające z przeładowanie operatora: () składnię intuicyjne i (b) możliwość intermix nowych typów z istniejących typów. Na przykład:  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
   static Vector* op_Addition( const Vector*, const Vector* );  
   static Vector* op_Subtraction( const Vector*, const Vector* );  
};  
  
int main()  
{  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc1 = Vector::op_Addition( pa, pb );  
   Vector *pc2 = Vector::op_Subtraction( pa, pc1 );  
   Vector *pc3 = Vector::op_Division( pc1, pc2->x );  
  
   if ( Vector::op_Equality( pc1, pc2 ))  
      ;  
}  
```  
  
 W nowej składni zwykle oczekiwań natywnego programisty C++ zostaną przywrócone, zarówno w deklaracji i użyj statycznych operatorów. Oto `Vector` klasy przetłumaczyć nowej składni:  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
   static Vector^ operator +( const Vector^, const Vector^ );  
   static Vector^ operator -( const Vector^, const Vector^ );  
};  
  
int main()  
{  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475,4.8916,-1.23 );  
  
   Vector^ pc1 = pa + pb;  
   Vector^ pc2 = pa - pc1;  
   Vector^ pc3 = pc1 / pc2->x;  
  
   if ( pc1 == pc2 )  
      ;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Deklaracje składowych w obrębie klasy lub interfejsu (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)