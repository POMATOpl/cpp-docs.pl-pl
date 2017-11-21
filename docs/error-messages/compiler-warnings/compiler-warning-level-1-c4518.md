---
title: "Kompilatora (poziom 1) ostrzeżenie C4518 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4518
dev_langs: C++
helpviewer_keywords: C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1e62727eae31387c70f1b25e5e028bc6afaf3665
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4518"></a>Kompilator C4518 ostrzegawcze (poziom 1)
"specyfikatora": Klasa magazynu lub wpisz specyfikator(y) nieoczekiwany; ignorowane  
  
 Poniższy przykład generuje C4518:  
  
```  
// C4518.cpp  
// compile with: /c /W1  
_declspec(dllexport) extern "C" void MyFunction();   // C4518  
  
extern "C" void MyFunction();   // OK  
```