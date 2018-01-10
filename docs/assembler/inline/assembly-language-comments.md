---
title: "Komentarze języka zestawu | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9ab1975a1146b598d7955d15b8e91a0f396724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="assembly-language-comments"></a>Komentarze języka zestawu
## <a name="microsoft-specific"></a>Specyficzne dla firmy Microsoft  
 Instrukcje w `__asm` blok służy komentarze języka zestawu:  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Ponieważ rozwinąć makra C w jednym wierszu logicznym, należy unikać komentarze języka zestawu w makrach. (Zobacz [Definiowanie bloków __asm jako makr C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) `__asm` Bloku może również zawierać komentarze w stylu języka C; Aby uzyskać więcej informacji, zobacz [przy użyciu języka C lub C++ w blokach __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **KOŃCOWY określonych firmy Microsoft**  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z języka Asembler w blokach __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)