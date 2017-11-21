---
title: "Kompilatora (poziom 1) ostrzeżenie C4227 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4227
dev_langs: C++
helpviewer_keywords: C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1d94ed5a5be12d3c439c43a34f982336b583abf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4227"></a>Kompilator C4227 ostrzegawcze (poziom 1)
użyto konstrukcji przestarzałej: kwalifikatory dla odwołania są ignorowane.  
  
 Przy użyciu kwalifikatory, takich jak `const` lub `volatile` z odwołaniami C++ jest przestarzała metoda.  
  
## <a name="example"></a>Przykład  
  
```  
// C4227.cpp  
// compile with: /W1 /c  
int j = 0;  
int &const i = j;   // C4227  
```