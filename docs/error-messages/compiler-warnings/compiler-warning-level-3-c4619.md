---
title: "Kompilatora (poziom 3) ostrzeżenie C4619 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4619
dev_langs:
- C++
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01f2b9d3e7cc935b100272e74c94da9dec5c5a92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4619"></a>Kompilator C4619 ostrzegawcze (poziom 3)
\#warning elementu pragma: istnieje ostrzeżenie o numerze "number"  
  
 Nastąpiła próba Aby wyłączyć ostrzeżenia, która nie istnieje.  
  
 To ostrzeżenie jest domyślnie wyłączone. Zobacz [kompilatora ostrzeżeń czy są wyłączone domyślnie](../../preprocessor/compiler-warnings-that-are-off-by-default.md) Aby uzyskać więcej informacji.  
  
 Poniższy przykład generuje C4619:  
  
```  
// C4619.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4619)  
#pragma warning(disable : 4354)   // C4619, C4354 does not exist  
```