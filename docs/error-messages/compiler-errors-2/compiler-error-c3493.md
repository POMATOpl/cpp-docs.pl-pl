---
description: 'Dowiedz się więcej o: błąd kompilatora C3493'
title: Błąd kompilatora C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: 8f16a53dbaf5b9924a4874d29d560f9c089eb244
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315533"
---
# <a name="compiler-error-c3493"></a>Błąd kompilatora C3493

nie można przechwycić "var", ponieważ nie określono żadnego domyślnego trybu przechwytywania

Puste wyrażenie lambda przechwytuje, `[]` określa, że wyrażenie lambda nie jawnie lub niejawnie nie przechwytuje żadnych zmiennych.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Określ domyślny tryb przechwytywania lub

- Jawnie Przechwyć co najmniej jedną zmienną.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3493, ponieważ modyfikuje zmienną zewnętrzną, ale określa pustą klauzulę przechwytywania:

```cpp
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

Poniższy przykład rozwiązuje C3493 przez określenie jako domyślny tryb przechwytywania.

```cpp
// C3493b.cpp

int main()
{
   int m = 55;
   [&](int n) { m = n; }(99);
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
