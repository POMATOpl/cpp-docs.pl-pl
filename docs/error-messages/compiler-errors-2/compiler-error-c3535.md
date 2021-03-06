---
description: 'Dowiedz się więcej o: błąd kompilatora C3535'
title: Błąd kompilatora C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: ba5019d623fe6f390051084894e13235c6503cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315351"
---
# <a name="compiler-error-c3535"></a>Błąd kompilatora C3535

nie można wywnioskować typu dla elementu "type1" z elementu "type2"

Nie można wywnioskować typu zmiennej zadeklarowanej za pomocą **`auto`** słowa kluczowego na podstawie typu wyrażenia inicjującego. Na przykład ten błąd występuje, gdy wyrażenie inicjacji daje w wyniku wartość **`void`** , która nie jest typem.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Upewnij się, że typ wyrażenia inicjowania nie jest **`void`** .

1. Upewnij się, że deklaracja nie jest wskaźnikiem do typu podstawowego. Aby uzyskać więcej informacji, zobacz [podstawowe typy](../../cpp/fundamental-types-cpp.md).

1. Upewnij się, że jeśli deklaracja jest wskaźnikiem do typu, wyrażenie inicjacji jest typem wskaźnika.

## <a name="examples"></a>Przykłady

Poniższy przykład daje C3535, ponieważ wyrażenie inicjacji daje w wyniku **`void`** .

```cpp
// C3535a.cpp
// Compile with /Zc:auto
void f(){}
int main()
{
   auto x = f();   //C3535
   return 0;
}
```

Poniższy przykład daje C3535, ponieważ instrukcja deklaruje zmienną `x` jako wskaźnik do typu wywnioskowanego, ale typ wyrażenia inicjatora jest podwójny. W związku z tym kompilator nie może wywnioskować typu zmiennej.

```cpp
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

Poniższy przykład daje C3535, ponieważ zmienna `p` deklaruje wskaźnik do typu wywnioskowanego, ale wyrażenie inicjacji nie jest typem wskaźnika.

```cpp
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)<br/>
[Typy podstawowe](../../cpp/fundamental-types-cpp.md)
