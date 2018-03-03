---
title: "Kompilatora (poziom 1) ostrzeżenie C4667 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4667
dev_langs:
- C++
helpviewer_keywords:
- C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d66b4e92eebecc746391add492222fd1779bf6ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4667"></a>Kompilator C4667 ostrzegawcze (poziom 1)
"Funkcja": Brak zdefiniowanego szablonu funkcji, która pasuje do wymuszonego wystąpienia  
  
 Nie można utworzyć wystąpienia szablonu funkcji, który nie został zadeklarowany.  
  
 Poniższy przykład powoduje C4667:  
  
```  
// C4667a.cpp  
// compile with: /LD /W1  
template  
void max(const int &, const int &); // C4667 expected  
```  
  
 Aby uniknąć tego ostrzeżenia, należy najpierw deklarować szablonu funkcji:  
  
```  
// C4667b.cpp  
// compile with: /LD  
// Declare the function template  
template<typename T>  
const T &max(const T &a, const T &b) {  
   return (a > b) ? a : b;  
}  
// Then forcibly instantiate it with a desired type ... i.e. 'int'  
//  
template  
const int &max(const int &, const int &);  
```