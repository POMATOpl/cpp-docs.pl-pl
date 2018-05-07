---
title: Kompilatora (poziom 1) ostrzeżenie C4508 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f152c2f3573e5f3bd7b8e9be0603ed6d3f11bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4508"></a>Kompilator C4508 ostrzegawcze (poziom 1)
"Funkcja": funkcja powinna zwrócić wartość; Założono typ zwracany "void"  
  
 Funkcja nie ma zwracanego typu określony. W takim przypadku C4430 również powinny wyzwalać i kompilator implementuje poprawka zgłoszone przez C4430 (wartość domyślna to int).  
  
 Aby usunąć to ostrzeżenie, jawnie deklarować zwracany typ funkcji.  
  
 Poniższy przykład generuje C4508:  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```