---
title: "C3369 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3369
dev_langs: C++
helpviewer_keywords: C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 62cd3de9bca4e695d051e150c7dfa45dca28936a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3369"></a>C3369 błąd kompilatora
"Nazwa modułu": idl_module już zdefiniowany  
  
 [Idl_module](../../windows/idl-module.md) użycia, w którym zdefiniować biblioteki DLL może występować tylko raz w programie.  
  
 Poniższy przykład generuje C3369:  
  
```  
// C3369.cpp  
// compile with: /c  
[idl_module(name="name1", dllname="x.dll")]; // C3369  
[idl_module(name="name1", dllname="x.dll")];  
```