---
title: Kompilatora (poziom 1) ostrzeżenie C4561 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4862d7f570faea3e362a505e67bddaf504b32de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4561"></a>Kompilator C4561 ostrzegawcze (poziom 1)
Wywołanie "__fastcall" niezgodny z "/ clr" opcja: konwertowanie na "\__stdcall"  
  
 [__Fastcall](../../cpp/fastcall.md) Konwencja wywoływania funkcji nie można używać z [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) — opcja kompilatora. Kompilator ignoruje wywołań `__fastcall`. Aby usunąć to ostrzeżenie, Usuń wywołania do **__fastcall** lub skompiluj bez **/CLR**.  
  
 Poniższy przykład generuje C4561:  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```