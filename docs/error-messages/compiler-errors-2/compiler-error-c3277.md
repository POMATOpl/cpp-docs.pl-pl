---
title: Błąd kompilatora C3277
ms.date: 11/04/2016
f1_keywords:
- C3277
helpviewer_keywords:
- C3277
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
ms.openlocfilehash: e49de69354d00babf8c6fa609e92153e88bf64c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530952"
---
# <a name="compiler-error-c3277"></a>Błąd kompilatora C3277

Nie można zdefiniować niezarządzanego wyliczenia "enum" wewnątrz zarządzanego "type"

Wyliczenie została niepoprawnie zdefiniowana wewnątrz typu zarządzanego.

Poniższy przykład spowoduje wygenerowanie C3277:

```
// C3277a.cpp
// compile with: /clr
ref class A
{
   enum E {e1,e2};   // C3277
   // try the following line instead
   // enum class E {e1,e2};
};

int main()
{
}
```
