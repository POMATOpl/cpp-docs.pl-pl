---
title: "Kompilatora (poziom 1) ostrzeżenie C4817 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4817
dev_langs: C++
helpviewer_keywords: C4817
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58ded9eec07b8c81349cde27580aa320b408adf5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4817"></a>Kompilator C4817 ostrzegawcze (poziom 1)
"członek": niedozwolone użycie "." można uzyskać dostępu do tego elementu członkowskiego; Kompilator zastąpione "->"  
  
 Użyto operatora dostępu do niewłaściwego elementu członkowskiego.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4817.  
  
```  
// C4817.cpp  
// compile with: /clr /W1  
using namespace System;  
int main() {  
   array<Int32> ^ a = gcnew array<Int32>(100);  
   Console::WriteLine( a.Length );   // C4817  
   Console::WriteLine( a->Length );   // OK  
}  
```  
