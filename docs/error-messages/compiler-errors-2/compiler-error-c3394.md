---
title: C3394 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3394
dev_langs:
- C++
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66d99ff65ba7fa6fd463a1266cdc506d7fd0a11b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251680"
---
# <a name="compiler-error-c3394"></a>C3394 błąd kompilatora
Błąd składni w klauzuli ograniczenia: znaleziono 'Identyfikator' oczekiwano typu  
  
 Ograniczenie został niewłaściwie sformatowany.  Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3394:  
  
```  
// C3394.cpp  
// compile with: /clr /c  
ref class MyClass {};  
ref class R {  
   generic<typename T>  
   where T : static   // C3394  
   // try the following line instead  
   // where T : MyClass  
   void f() {}  
};  
```