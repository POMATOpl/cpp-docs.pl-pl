---
title: "C3235 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3235
dev_langs: C++
helpviewer_keywords: C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43be37f86df82117896efd51be1a69e8d7ee853a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3235"></a>C3235 błąd kompilatora
"specjalizacja": jawna lub częściowa specjalizacja klasy generycznej jest niedozwolona.  
  
 Klasy ogólne nie może służyć do specjalizacji jawna lub częściowa.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3235.  
  
```  
// C3235.cpp  
// compile with: /clr  
generic<class T>  
public ref class C {};  
  
generic<>  
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.  
```