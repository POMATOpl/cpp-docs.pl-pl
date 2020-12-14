---
description: 'Dowiedz się więcej o: błąd kompilatora C3537'
title: Błąd kompilatora C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 84440b757b85a59f87fcca064911136da6cce269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315260"
---
# <a name="compiler-error-c3537"></a>Błąd kompilatora C3537

"Type": nie można rzutować na typ, który zawiera wartość "Auto"

Nie można rzutować zmiennej do wskazanego typu, ponieważ typ zawiera **`auto`** słowo kluczowe i domyślną wartość [/Zc:](../../build/reference/zc-auto-deduce-variable-type.md) autokompilator jest włączona.

## <a name="example"></a>Przykład

Poniższy kod daje C3537, ponieważ zmienne są rzutowane na typ, który zawiera **`auto`** słowo kluczowe.

```cpp
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)
