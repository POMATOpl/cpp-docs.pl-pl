---
title: "C3141 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3141
dev_langs: C++
helpviewer_keywords: C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00266db4fde48b175b9374ca31a89b15ca13ced2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3141"></a>C3141 błąd kompilatora
"nazwa_interfejsu": interfejsy obsługują tylko publiczne dziedziczenie  
  
 Zdefiniowane za pomocą interfejsów [interfejsu (lub __interface)](../../cpp/interface.md) — słowo kluczowe obsługują tylko publiczne dziedziczenie.  
  
 Poniższy przykład generuje C3141:  
  
```  
// C3141.cpp  
__interface IBase {};  
__interface IDerived1 : protected IBase {};  // C3141  
__interface IDerived2 : private IBase {};    // C3141  
```