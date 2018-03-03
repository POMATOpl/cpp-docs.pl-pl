---
title: "C2691 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2691
dev_langs:
- C++
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc1c8db55cee6a7a3f9f59504f8b9a178af798b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2691"></a>C2691 błąd kompilatora
"typ danych": zarządzanego lub WinRTarray nie może posiadać tego typu elementu  
  
 Typ zarządzany lub element tablicy WinRT może być typem wartości lub typ referencyjny.  
  
 Poniższy przykład generuje C2691:  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
