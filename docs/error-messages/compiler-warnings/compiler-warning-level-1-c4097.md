---
title: "Kompilatora (poziom 1) ostrzeżenie C4097 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4097
dev_langs:
- C++
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f900ac783e5d7f1901e42577e750b524afddcb44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4097"></a>Kompilator C4097 ostrzegawcze (poziom 1)
Oczekiwano wartości parametru pragma "Restore" lub "off"  
  
 Pragma została przekazana nieprawidłowa wartość.  
  
 Poniższy przykład generuje C4097:  
  
```  
// C4097.cpp  
// compile with: /W1  
#pragma runtime_checks("",test)   // C4097  
// try the following line instead  
// #pragma runtime_checks("",off)  
  
int main() {  
}  
```