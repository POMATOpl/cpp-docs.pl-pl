---
title: C3100 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3100
dev_langs:
- C++
helpviewer_keywords:
- C3100
ms.assetid: 7a9c9eaf-08ef-442d-94a0-e457beee8549
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d28412fed7b31a81a0ef49d9e29c917f4c617e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254300"
---
# <a name="compiler-error-c3100"></a>C3100 błąd kompilatora
'target': nieznany kwalifikator atrybutu  
  
 Określono nieprawidłowy element docelowy atrybutu.  
  
 Aby uzyskać więcej informacji, zobacz [zdefiniowane przez użytkownika atrybuty](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3100.  
  
```  
// C3100.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::All)]  
public ref class Attr : public Attribute {  
public:  
   Attr(int t) : m_t(t) {}  
   int m_t;  
};  
  
[invalid_target:Attr(10)];   // C3100  
[assembly:Attr(10)];   // OK  
```