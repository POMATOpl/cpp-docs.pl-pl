---
title: "C3868 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3868
dev_langs: C++
helpviewer_keywords: C3868
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3fc2ce896658468e1ae53638512d92d925f0362a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3868"></a>C3868 błąd kompilatora
'type': ograniczenia na parametry generyczne "parameter" różnią się od tych w deklaracji  
  
 Wiele deklaracje muszą mieć takich samych ograniczeń ogólnych.  Aby uzyskać więcej informacji, zobacz [ogólne](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3868.  
  
```  
// C3868.cpp  
// compile with: /clr /c  
interface struct I1;  
  
generic <typename T> ref struct MyStruct;  
generic <typename U> where U : I1 ref struct MyStruct;   // C3868  
  
// OK  
generic <typename T> ref struct MyStruct2;  
generic <typename U> ref struct MyStruct2;  
  
generic <typename T> where T : I1 ref struct MyStruct3;  
generic <typename U> where U : I1 ref struct MyStruct3;  
```