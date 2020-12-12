---
description: 'Dowiedz się więcej o: notablicę'
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 2c818d07603e294f760b768861ce7e7a3e02894b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146201"
---
# <a name="novtable"></a>novtable

**Specyficzne dla firmy Microsoft**

Jest to **`__declspec`** rozszerzony atrybut.

Ten formularz **`__declspec`** może być stosowany do dowolnej deklaracji klasy, ale powinien być stosowany tylko do czystych klas interfejsów, czyli klas, które nigdy nie zostaną utworzone samodzielnie. **`__declspec`** Uniemożliwia kompilatorowi generowanie kodu w celu zainicjowania vfptr w konstruktorach i destruktorze klasy. W wielu przypadkach powoduje to usunięcie tylko odwołań do tablic wirtualnych, które są skojarzone z klasą, a w rezultacie konsolidator usunie. Użycie tej formy **`__declspec`** może spowodować znaczny spadek rozmiaru kodu.

Jeśli spróbujesz utworzyć wystąpienie klasy oznaczonej przez, **`novtable`** a następnie uzyskać dostęp do elementu członkowskiego klasy, otrzymasz naruszenie dostępu (AV).

## <a name="example"></a>Przykład

```cpp
// novtable.cpp
#include <stdio.h>

struct __declspec(novtable) X {
   virtual void mf();
};

struct Y : public X {
   void mf() {
      printf_s("In Y\n");
   }
};

int main() {
   // X *pX = new X();
   // pX->mf();   // Causes a runtime access violation.

   Y *pY = new Y();
   pY->mf();
}
```

```Output
In Y
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[`__declspec`](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
