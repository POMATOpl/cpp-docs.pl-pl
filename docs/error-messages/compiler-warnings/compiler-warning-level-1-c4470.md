---
title: "Kompilatora (poziom 1) ostrzeżenie C4470 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4470
dev_langs: C++
helpviewer_keywords: C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 627e26ff805a24d4de3c6fef77976da97efe55b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4470"></a>Kompilator C4470 ostrzegawcze (poziom 1)
Formant zmiennoprzecinkowych pragm zignorowane z opcją/CLR  
  
 Formant liczb zmiennoprzecinkowych pragm:  
  
-   [fenv_access](../../preprocessor/fenv-access.md)  
  
-   [float_control](../../preprocessor/float-control.md)  
  
-   [fp_contract](../../preprocessor/fp-contract.md)  
  
 nie obowiązują w obszarze [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Poniższy przykład generuje C4470:  
  
```  
// C4470.cpp  
// compile with: /clr /W1 /LD  
#pragma float_control(except, on)   // C4470  
```