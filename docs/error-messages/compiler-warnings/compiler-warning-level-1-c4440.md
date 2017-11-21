---
title: "Kompilatora (poziom 1) ostrzeżenie C4440 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4440
dev_langs: C++
helpviewer_keywords: C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9557791e98a2f3e5ecf58b44170b5c99fb8e30c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4440"></a>Kompilator C4440 ostrzegawcze (poziom 1)
wywoływanie definicję Konwencji wywołań z "calling_convention1" do "calling_convention2" ignorowane  
  
 Próba zmiany Konwencja wywoływania została zignorowana.  
  
 Poniższy przykład generuje C4440:  
  
```  
// C4440.cpp  
// compile with: /W1 /LD /clr  
typedef void __clrcall F();  
typedef F __cdecl *PFV;   // C4440  
```