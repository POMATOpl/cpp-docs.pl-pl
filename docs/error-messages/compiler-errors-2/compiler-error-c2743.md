---
description: 'Dowiedz się więcej o: błąd kompilatora C2743'
title: Błąd kompilatora C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 2619d4a0dd2b89d36f11944b59c2ab4993d95fd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123061"
---
# <a name="compiler-error-c2743"></a>Błąd kompilatora C2743

"Type": nie można przechwycić natywnego typu z __clrcall destruktorem lub konstruktorem kopiującym

Moduł skompilowany za pomocą **/CLR** próbował przechwycić wyjątek typu natywnego i gdzie destruktor lub Konstruktor kopiujący typu używa `__clrcall` konwencji wywoływania.

Podczas kompilowania z **/CLR** obsługa wyjątków oczekuje, że funkcje składowe w typie natywnym mają być [__cdecl](../../cpp/cdecl.md) , a nie [__clrcall](../../cpp/clrcall.md). Typy natywne z funkcjami składowymi używającymi `__clrcall` konwencji wywoływania nie mogą być przechwytywane w module skompilowanym za pomocą **/CLR**.

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2743.

```cpp
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```
