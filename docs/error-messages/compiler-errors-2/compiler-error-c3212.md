---
title: C3212 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3212
dev_langs:
- C++
helpviewer_keywords:
- C3212
ms.assetid: 9e271bb6-a51f-4b96-b26b-9f4ca28fca0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3205873a4dfe0eae7284698d310a9c5fb5f474b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256168"
---
# <a name="compiler-error-c3212"></a>C3212 błąd kompilatora
"specjalizacja": jawna specjalizacja szablonu elementu członkowskiego musi być elementem członkowskim jawnej specjalizacji  
  
 Jawna specjalizacja został niewłaściwie sformatowany.  
  
 Poniższy przykład generuje C3212:  
  
```  
// C3212.cpp  
// compile with: /LD  
template <class T>  
struct S {  
   template <class T1>  
   struct S1;  
};  
  
template <class T>   // C3212  
template <>  
struct S<T>::S1<int> {};  
  
/*  
// try the following instead  
template <>  
template <>  
struct S<int>::S1<int> {};  
*/  
  
/*  
// or, the following  
template <>  
struct S<int> {  
   template <class T1>  
   struct S1;  
};  
  
template <>  
struct S<int>::S1<int> {  
};  
*/  
```