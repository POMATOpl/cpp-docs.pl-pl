---
title: Kompilatora (poziom 1) ostrzeżenie C4068 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4068
dev_langs:
- C++
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37860067c8ff5409fd4376638ef1754673bca93b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279412"
---
# <a name="compiler-warning-level-1-c4068"></a>Kompilator C4068 ostrzegawcze (poziom 1)
Nieznana wartość dyrektywy pragma  
  
 Kompilator ignorowane nierozpoznany [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md). Upewnij się, **pragma** jest dozwolona przez kompilator używasz. Poniższy przykład generuje C4068:  
  
```  
// C4068.cpp  
// compile with: /W1  
#pragma NotAValidPragmaName   // C4068, use valid name to resolve  
int main()  
{  
}  
```