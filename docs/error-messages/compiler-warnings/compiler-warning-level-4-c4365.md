---
title: Kompilatora (poziom 4) ostrzeżenie C4365 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4365
dev_langs:
- C++
helpviewer_keywords:
- C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 496f26046803efdd2b67cdc6d5a5ec74a3cbb90d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4365"></a>Kompilator C4365 ostrzegawcze (poziom 4)
"Akcja": konwersja z "type_1" na "type_2", niezgodność signed/unsigned  
  
 Na przykład próbowano przekonwertować wartość bez znaku wartość podpisem.  
  
 C4365 jest domyślnie wyłączone.  Aby uzyskać więcej informacji, zobacz [kompilatora ostrzeżeń czy są wyłączone domyślnie](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4365.  
  
```  
// C4365.cpp  
// compile with: /W4  
#pragma warning(default:4365)  
  
int f(int) { return 0; }  
void Test(size_t i) {}  
  
int main() {  
   unsigned int n = 10;  
   int o = 10;  
   n++;  
   f(n);   // C4365  
   f(o);   // OK  
  
   Test( -19 );   // C4365  
}  
```