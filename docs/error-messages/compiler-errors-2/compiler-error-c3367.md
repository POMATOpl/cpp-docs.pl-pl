---
description: 'Dowiedz się więcej o: błąd kompilatora C3367'
title: Błąd kompilatora C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: cd428bb0472ab9cb621f85ac684cbb4d9bbc12d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245281"
---
# <a name="compiler-error-c3367"></a>Błąd kompilatora C3367

"static_member_function": nie można użyć funkcji statycznej w celu utworzenia niepowiązanego delegata

Gdy wywołujesz niepowiązanego delegata, musisz przekazać wystąpienie obiektu. Ze względu na to, że statyczna funkcja członkowska jest wywoływana za pomocą nazwy klasy, można utworzyć jedynie wystąpienie niepowiązanego delegata z funkcją członkowską wystąpienia.

Aby uzyskać więcej informacji na temat niezwiązanych delegatów, zobacz [How to: define and use delegats (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3367.

```cpp
// C3367.cpp
// compile with: /clr
ref struct R {
   void b() {}
   static void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::b);   // OK
   Del ^ b = gcnew Del(&R::f);   // C3367
}
```
