---
description: 'Dowiedz się więcej o: błąd kompilatora C3834'
title: Błąd kompilatora C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 4cf0bc5e3587e77d8ad31fc4e2fd2cf0130aa781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249181"
---
# <a name="compiler-error-c3834"></a>Błąd kompilatora C3834

niedozwolone jawne rzutowanie do przypiętego wskaźnika; Zamiast tego użyj przypiętej zmiennej lokalnej

Jawne rzutowanie na przypięty wskaźnik jest niedozwolone.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3834.

```cpp
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
