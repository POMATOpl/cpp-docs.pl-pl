---
description: 'Dowiedz się więcej o: błąd kompilatora C2346'
title: Błąd kompilatora C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: eb2bbda6c7f7e0c9213b35a794b915967d03321f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298373"
---
# <a name="compiler-error-c2346"></a>Błąd kompilatora C2346

nie można skompilować "Function" jako natywny: Przyczyna

Kompilator nie może skompilować funkcji do MSIL.

Aby uzyskać więcej informacji, zobacz [Managed, niezarządzane](../../preprocessor/managed-unmanaged.md) i [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Usuń kod w funkcji, której nie można skompilować do MSIL.

1. Nie Kompiluj modułu z **/CLR** lub Oznacz funkcję jako niezarządzaną z niezarządzaną pragmą.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2346.

```cpp
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

int main()
{
   S s;
}
```
