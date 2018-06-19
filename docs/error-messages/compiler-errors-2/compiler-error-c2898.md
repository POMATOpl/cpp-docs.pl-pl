---
title: C2898 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2898
dev_langs:
- C++
helpviewer_keywords:
- C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3299e3c341657fd253e688065014b46519dce5eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241121"
---
# <a name="compiler-error-c2898"></a>C2898 błąd kompilatora
"deklaracją": Szablony funkcji Członkowskich nie może być wirtualny  
  
 Poniższy przykład generuje C2898:  
  
```  
// C2898.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> virtual void f(T t) {}   // C2898  
};  
```