---
title: "C3624 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3624
dev_langs: C++
helpviewer_keywords: C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6f148b2bfc0f1f43135e05b32625bf87e420a71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3624"></a>C3624 błąd kompilatora
'type': Użyj tego typu wymaga odwołania do zestawu "assembly"  
  
 Nie określono zestawu (odwołanie) wymagane do kompilacji kodu. zestaw do przekazania [#using](../../preprocessor/hash-using-directive-cpp.md) dyrektywy.  
  
## <a name="example"></a>Przykład  
Poniższy przykład generuje C3624:  
  
```  
// C3624.cpp  
// compile with: /clr /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public ref class MyForm : public Windows::Forms::Form {};   // C3624  
```  
