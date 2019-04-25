---
title: Błąd kompilatora C2470
ms.date: 11/04/2016
f1_keywords:
- C2470
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
ms.openlocfilehash: 2a4f8c8052081fe90801dfeb30d942fbb9a91a01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303115"
---
# <a name="compiler-error-c2470"></a>Błąd kompilatora C2470

'Funkcja': wygląda jak definicja funkcji, ale nie ma żadnej listy parametrów; Pomijanie widocznej treści

Definicja funkcji brakuje listy argumentów.

Poniższy przykład spowoduje wygenerowanie C2470:

```
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```