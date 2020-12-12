---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4481'
title: Ostrzeżenie kompilatora (poziom 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: 463df18090a4f6f632a80543576db4cb9048e754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251300"
---
# <a name="compiler-warning-level-4-c4481"></a>Ostrzeżenie kompilatora (poziom 4) C4481

użyto niestandardowego rozszerzenia: override specyfikator "słowo kluczowe"

Użyto słowa kluczowego, które nie jest w standardzie C++, na przykład jeden z specyfikatorów przesłonięcia, które również działa w obszarze/CLR.  Aby uzyskać więcej informacji, zobacz,

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Specyfikatory przesłonięcia](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>Przykład

Poniższy przykład generuje C4481.

```cpp
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```
