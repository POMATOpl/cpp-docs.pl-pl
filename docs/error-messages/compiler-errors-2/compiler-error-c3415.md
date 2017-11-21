---
title: "C3415 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3415
dev_langs: C++
helpviewer_keywords: C3415
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9a03e0dbb61dc6f57b1a6fe3cd345d46f78b05a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3415"></a>C3415 błąd kompilatora
"section_name" znaleziono wiele sekcji z różnymi atrybutami (wartość)  
  
 Wartości powodujące konflikt zostały określone w [sekcji](../../preprocessor/section.md) pragm.  
  
 `value`jest bieżące ustawienia dla sekcji, jak określono w ntimage.h. Na przykład:  
  
```  
// Section contains extended relocations.  
#define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000    
// Section can be discarded.  
#define IMAGE_SCN_MEM_DISCARDABLE            0x02000000    
// Section is not cachable.  
#define IMAGE_SCN_MEM_NOT_CACHED             0x04000000    
// Section is not pageable.  
#define IMAGE_SCN_MEM_NOT_PAGED              0x08000000    
// Section is shareable.  
#define IMAGE_SCN_MEM_SHARED                 0x10000000    
// Section is executable.  
#define IMAGE_SCN_MEM_EXECUTE                0x20000000    
// Section is readable.  
#define IMAGE_SCN_MEM_READ                   0x40000000    
// Section is writeable.  
#define IMAGE_SCN_MEM_WRITE                  0x80000000    
```  
  
 Poniższy przykład generuje C3415:  
  
```  
// C3415.cpp  
#pragma section("mysec1",write)  
#pragma section("mysec1",read)   // C3415  
```