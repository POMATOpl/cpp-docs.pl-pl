---
description: 'Dowiedz się więcej o: błąd kompilatora C3893'
title: Błąd kompilatora C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 975e2e356bc4b98a25a80e8ae4cc152c3b9b3207
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119921"
---
# <a name="compiler-error-c3893"></a>Błąd kompilatora C3893

"var": wykorzystanie wartości l składowej danych initonly jest dozwolone tylko w konstruktorze wystąpienia klasy "type_name"

Statyczne składowe danych [initonly](../../dotnet/initonly-cpp-cli.md) mogą mieć tylko adresy wykonywane w konstruktorze statycznym.

Elementy członkowskie danych initonly wystąpienia (niestatyczne) mogą mieć tylko ich adresy w konstruktorach wystąpień (niestatycznych).

Poniższy przykład generuje C3893:

```cpp
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```
