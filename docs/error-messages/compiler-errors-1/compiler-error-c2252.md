---
title: Błąd kompilatora C2252 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2252
dev_langs:
- C++
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31fb5b48f322fbce71f1b830a01e428930937958
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041379"
---
# <a name="compiler-error-c2252"></a>Błąd kompilatora C2252

Nie można jawnie utworzyć wystąpienia szablonu w bieżącym zakresie

Kompilator wykrył problem z jawne utworzenie wystąpienia szablonu.  Na przykład nie można jawnie tworzenia wystąpienia szablonu funkcji.

Poniższy przykład spowoduje wygenerowanie C2252:

```
// C2252.cpp
class A {
public:
   template <class T>
   int getit(int i , T * it ) {
      return i;
   }
   template int A::getit<double>(int i, double * it);   // C2252
   // try the following line instead
   // template <> int A::getit<double>(int i, double * it);

};

int main() {
   // cannot explicitly instantiate in function
   template int A::getit<long>(int i, long * it);   // C2252
}
```