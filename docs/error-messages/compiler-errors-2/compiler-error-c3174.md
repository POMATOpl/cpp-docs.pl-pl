---
title: C3174 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3174
dev_langs:
- C++
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b8898bc2079c3f62c2c1db1ac2a7420db7be7f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252621"
---
# <a name="compiler-error-c3174"></a>C3174 błąd kompilatora
Atrybut modułu nie została określona.  
  
 Program, który używa atrybutów języka Visual C++ również nie użyto [modułu](../../windows/module-cpp.md) atrybut, który jest wymagany w program, który używa atrybutów.  
  
 Poniższy przykład generuje C3174:  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```