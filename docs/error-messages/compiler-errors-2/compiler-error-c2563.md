---
title: C2563 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85a4de195c681ce8d11b789a9aca102629cc2bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228598"
---
# <a name="compiler-error-c2563"></a>C2563 błąd kompilatora
niezgodność w liście formalnych parametrów  
  
 Lista parametrów formalnych funkcji (lub wskaźnika do funkcji) nie odpowiadają innej funkcji (lub wskaźnika do funkcji członkowskiej). W związku z tym nie można wykonać przypisania, funkcji lub wskaźników.  
  
 Poniższy przykład generuje C2563:  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```