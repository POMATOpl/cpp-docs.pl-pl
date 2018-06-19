---
title: Kompilatora (poziom 4) ostrzeżenie C4626 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4626
dev_langs:
- C++
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e43aa93a2f40d97ef3db5c2f556b04e84512724
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295139"
---
# <a name="compiler-warning-level-4-c4626"></a>Kompilator C4626 ostrzegawcze (poziom 4)
"pochodzi z klasy": operator przypisania został niejawnie zdefiniowany jako usunięty, ponieważ operator przypisania klasa podstawowa jest niedostępne lub zostały usunięte  
  
 Operator przypisania został usunięty lub nie jest dostępna w klasie podstawowej i dlatego nie został wygenerowany dla klasy pochodnej. Błąd kompilatora spowoduje, że wszelkie próby przypisać obiekty tego typu.  
  
 To ostrzeżenie jest domyślnie wyłączone. Zobacz [kompilatora ostrzeżeń czy są wyłączone domyślnie](../../preprocessor/compiler-warnings-that-are-off-by-default.md) Aby uzyskać więcej informacji.  
  
 Poniższy przykład generuje C4626 i pokazuje, jak rozwiązywanie problemu:  
  
```  
// C4626  
// compile with: /W4  
#pragma warning(default : 4626)  
class B  
{  
// public:  
   B& operator = (const B&)  
   {  
      return *this;  
   }  
};  
  
class D : public B  
{  
  
}; // C4626 - to fix, make B's copy constructor public  
  
int main()  
{  
   D m;  
   D n;  
   // m = n;   // this line will cause an error  
}  
```