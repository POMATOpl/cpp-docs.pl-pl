---
title: C3214 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3214
dev_langs:
- C++
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73141b896088ff286d4b34b3bb3e2a00c2036903
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248730"
---
# <a name="compiler-error-c3214"></a>C3214 błąd kompilatora
'type': nieprawidłowy typ argumentu dla parametru ogólnego "param" Ogólne "generic_type" nie spełnia ograniczenia "ograniczenia"  
  
 Typ został określony dla wystąpienia klasy generycznej, który nie spełnia ograniczenia klasy ogólnego.  
  
 Poniższy przykład generuje C3214:  
  
```  
// C3214.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>   
where T : A  
ref class C {};  
  
ref class X : public A {};  
  
int main() {  
   C<int>^ c = new C<int>;   // C3214  
   C<X ^> ^ c2 = new C<X^>;   // OK  
}  
```