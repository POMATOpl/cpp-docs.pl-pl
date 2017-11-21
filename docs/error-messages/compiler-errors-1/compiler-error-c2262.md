---
title: "C2262 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2262
dev_langs: C++
helpviewer_keywords: C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 216a82734603db0fd62692f7818dcb1e1fa67b06
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2262"></a>C2262 błąd kompilatora
"attribute_specifiers": Deklaracje InternalsVisibleTo nie mogą mieć wersji, kultury ani architektury procesora określona  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Atrybutu nie została poprawnie określona.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2262.  
  
```  
// C2262.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262  
[assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```