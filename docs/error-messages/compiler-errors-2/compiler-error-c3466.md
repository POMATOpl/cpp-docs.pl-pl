---
title: "C3466 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3466
dev_langs:
- C++
helpviewer_keywords:
- C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af992f70d3e2a673c098d3e412e6368dc2f64b02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3466"></a>C3466 błąd kompilatora
"type": specjalizacji klasy generycznej nie może być przekazywany  
  
 Nie można użyć typu przekazywania na specjalizacji klasy generycznej.  
  
 Aby uzyskać więcej informacji, zobacz [przesyłania dalej typu (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy składnik.  
  
```  
// C3466.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3466.  
  
```  
// C3466_b.cpp  
// compile with: /clr /c  
#using "C3466.dll"  
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```