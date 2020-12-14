---
description: 'Dowiedz się więcej o: błąd kompilatora C3821'
title: Błąd kompilatora C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 745efeb21933e06f65f9e700ad5780da8234da90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249376"
---
# <a name="compiler-error-c3821"></a>Błąd kompilatora C3821

"Function": typ zarządzany lub funkcja nie może być użyta w funkcji niezarządzanej

Funkcje z zestawem wbudowanym lub [setjmp](../../c-runtime-library/reference/setjmp.md) nie mogą zawierać typów wartości ani klas zarządzanych. Aby naprawić ten błąd, Usuń Wbudowany zestaw i `setjmp` lub Usuń obiekty zarządzane.

C3821 może również wystąpić, jeśli spróbujesz użyć automatycznego magazynu w funkcji vararg.  Aby uzyskać więcej informacji, zobacz [listę zmiennych argumentów (...) (c++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) i [semantykę stosu C++ dla typów referencyjnych](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3821.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

Poniższy przykład generuje C3821.

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
