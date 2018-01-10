---
title: "C3292 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3292
dev_langs: C++
helpviewer_keywords: C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eddab20396122ed6b3b8f7c75ccda17ad2a0c684
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3292"></a>C3292 błąd kompilatora
Nie można ponownie otworzyć przestrzeni nazw cli  
  
 Nie można zadeklarować przestrzeni nazw cli w kodzie.  Aby uzyskać więcej informacji, zobacz [platformy, domyślna i cli przestrzenie nazw](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3292.  
  
```  
// C3292.cpp  
// compile with: /clr /c  
namespace cli {};   // C3292  
```