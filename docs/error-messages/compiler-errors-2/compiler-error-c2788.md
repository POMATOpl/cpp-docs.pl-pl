---
title: C2788 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2788
dev_langs:
- C++
helpviewer_keywords:
- C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd6843eb1f1fba77cc272361dc3dc7c688789b12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236706"
---
# <a name="compiler-error-c2788"></a>C2788 błąd kompilatora
'Identyfikator': więcej niż jeden GUID skojarzony z tym obiektem  
  
 [__Uuidof](../../cpp/uuidof-operator.md) operator przyjmuje typu zdefiniowanego przez użytkownika z identyfikatorem GUID dołączona lub takie zdefiniowane przez użytkownika typu obiektu. Ten błąd występuje, gdy argument jest obiekt o wiele identyfikatorów GUID.  
  
 Poniższy przykład generuje C2788:  
  
```  
// C2788.cpp  
#include <windows.h>  
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};  
template <class T, class U> class MyClass {};  
  
typedef MyClass<A,B> MyBadClass;  
typedef MyClass<A,A> MyGoodClass;  
  
int main() {  
   __uuidof(MyBadClass);    // C2788  
   // try the following line instead  
   __uuidof(MyGoodClass);  
}  
```