---
title: Kompilatora (poziom 4) ostrzeżenie C4516 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4516
dev_langs:
- C++
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5ca56734d5bd9f2ddf66732ed894d805e368664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295174"
---
# <a name="compiler-warning-level-4-c4516"></a>Kompilator C4516 ostrzegawcze (poziom 4)
"class::symbol": deklaracje dostępu są przestarzałe; deklaracje using elementu członkowskiego zapewniają lepszą alternatywę  
  
 Komitet ANSI C++ został zadeklarowany deklaracje dostępu (zmienianie dostępu do elementu członkowskiego w klasie pochodnej bez [przy użyciu](../../cpp/using-declaration.md) — słowo kluczowe) być nieaktualne. Deklaracje dostępu może być nieobsługiwana w przyszłych wersjach programu C++.  
  
 Poniższy przykład generuje C4516:  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```