---
description: 'Dowiedz się więcej o: błąd kompilatora C3162'
title: Błąd kompilatora C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: ca44b27607a34a469a5fd6fc1371e1510452247a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242317"
---
# <a name="compiler-error-c3162"></a>Błąd kompilatora C3162

"Type": typu referencyjnego, który ma destruktor, nie można użyć jako typu statycznej składowej danych "member"

Środowisko uruchomieniowe języka wspólnego nie może wiedzieć, kiedy należy uruchomić destruktor zdefiniowany przez użytkownika, gdy Klasa zawiera również statyczną funkcję członkowską.

Destruktor nigdy nie będzie uruchamiany, chyba że obiekt zostanie jawnie usunięty.

Aby uzyskać więcej informacji, zobacz,

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Typowe problemy przy migracji Visual C++ w wersji 64-bitowej](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Przykład

Poniższy przykład generuje C3162.

```cpp
// C3162.cpp
// compile with: /clr /c
ref struct A {
   ~A() { System::Console::WriteLine("in destructor"); }
   static A i;   // C3162
   static A^ a = gcnew A;   // OK
};

int main() {
   A ^ a = gcnew A;
   delete a;
}
```
