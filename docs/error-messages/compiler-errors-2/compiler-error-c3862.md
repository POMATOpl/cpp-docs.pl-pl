---
title: "C3862 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3862
dev_langs: C++
helpviewer_keywords: C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63fa12348ee2ab58782fad02719918bfe7929ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3862"></a>C3862 błąd kompilatora
"Funkcja": nie można kompilować niezarządzanej funkcji z/CLR: pure lub/CLR: Safe  
  
 **/CLR: pure** i **/CLR: Safe** — opcje kompilatora zostały uznane za przestarzałe w programie Visual Studio 2015.  
  
 Kompilacja z **/CLR: pure** lub **/CLR: Safe** utworzy obraz tylko MSIL obrazu bez natywnego kodu (niezarządzany).  W związku z tym nie można użyć `unmanaged` pragma w **/CLR: pure** lub **/CLR: Safe** kompilacji.  
  
 Aby uzyskać więcej informacji, zobacz [/CLR (kompilacja języka wspólnego środowiska uruchomieniowego)](../../build/reference/clr-common-language-runtime-compilation.md) i [zarządzane, niezarządzane](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3862:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```