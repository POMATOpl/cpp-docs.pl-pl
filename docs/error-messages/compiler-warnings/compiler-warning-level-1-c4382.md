---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4382'
title: Ostrzeżenie kompilatora (poziom 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: 038225aea9592070b44af138be9deb5076e2f5f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311308"
---
# <a name="compiler-warning-level-1-c4382"></a>Ostrzeżenie kompilatora (poziom 1) C4382

> Zgłaszanie elementu "*Type*": typ z destruktorem __clrcall lub konstruktorem kopiującym można przechwycić tylko w module/CLR: Pure

## <a name="remarks"></a>Uwagi

**/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

Podczas kompilowania z **/CLR** (nie **/CLR: Pure**), obsługa wyjątków oczekuje, że funkcje składowe w typie natywnym mają być [__cdecl](../../cpp/cdecl.md) , a nie [__clrcall](../../cpp/clrcall.md). Typy natywne z funkcjami składowymi używającymi `__clrcall` konwencji wywoływania nie mogą być przechwytywane w module skompilowanym za pomocą **/CLR**.

Jeśli wyjątek zostanie przechwycony w module skompilowanym za pomocą **/CLR: Pure**, można zignorować to ostrzeżenie.

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4382.

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```
