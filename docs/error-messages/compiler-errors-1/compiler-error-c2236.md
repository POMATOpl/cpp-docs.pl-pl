---
title: "C2236 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2236
dev_langs: C++
helpviewer_keywords: C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: afac29b06d99ceca65aec2f04df8824f58405581
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2236"></a>C2236 błąd kompilatora
Nieoczekiwany token 'Identyfikator'. Zapomnialeś ';'?  
  
 Identyfikator jest już zdefiniowany jako typ i nie może zostać zastąpiona przez typu zdefiniowanego przez użytkownika.  
  
 Poniższy przykład generuje C2236:  
  
```  
// C2236.cpp  
// compile with: /c  
int class A {};  // C2236 "int class" is unexpected  
int i;  
class B {};  
```