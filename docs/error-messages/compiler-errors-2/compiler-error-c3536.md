---
description: 'Dowiedz się więcej o: błąd kompilatora C3536'
title: Błąd kompilatora C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: 62bd8bb75adfbf0e21f150f4240bb5f4011f6382
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112508"
---
# <a name="compiler-error-c3536"></a>Błąd kompilatora C3536

"symbol": nie można użyć, zanim zostanie zainicjowany

Nie można użyć wskazanego symbolu przed jego zainicjowaniem. W tym przypadku oznacza to, że zmienna nie może zostać użyta do zainicjowania siebie.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Nie Inicjuj inicjacji zmiennej.

## <a name="example"></a>Przykład

Poniższy przykład daje C3536, ponieważ każda zmienna jest inicjowana z samym sobą.

```cpp
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)
