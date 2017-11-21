---
title: "Kompilatora (poziom 1) ostrzeżenie C4810 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4810
dev_langs: C++
helpviewer_keywords: C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65c9c51a7672bea5d6aec81d8b1ee2363519e488
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4810"></a>Kompilator C4810 ostrzegawcze (poziom 1)
Wartość dyrektywy pragma pack(show) == n  
  
 To ostrzeżenie zostanie wyświetlone, korzystając z **Pokaż** opcji [pakietu](../../preprocessor/pack.md) pragma. *n*jest to wartość bieżącego pakietu.  
  
 Na przykład poniższy kod przedstawia, jak ostrzeżenie C4810 współpracuje z dodatkiem Service pack pragma:  
  
```  
// C4810.cpp  
// compile with: /W1 /LD  
// C4810 expected  
#pragma pack(show)  
#pragma pack(4)  
#pragma pack(show)  
```