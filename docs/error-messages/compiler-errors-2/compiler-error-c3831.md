---
title: "C3831 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3831
dev_langs:
- C++
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4779779f48bd01d2d5d42abddc5f24dcb10d19f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3831"></a>C3831 błąd kompilatora
"członek": "class" nie może mieć przypiętego elementu członkowskiego danych lub funkcji członkowskiej zwracającej przypięty wskaźnik  
  
 [pin_ptr (C + +/ CLI)](../../windows/pin-ptr-cpp-cli.md) zostało niepoprawnie użyte.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3831:  
  
```  
// C3831a.cpp  
// compile with: /clr  
ref class Y  
{  
public:  
   int i;  
};  
  
ref class X  
{  
   pin_ptr<int> mbr_Y;   // C3831  
   int^ mbr_Y2;   // OK  
};  
  
int main() {  
   Y y;  
   pin_ptr<int> p = &y.i;  
}  
```  
