---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2020'
title: Błąd narzędzi konsolidatora LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 61e999b2f451359e3a806bc2da5f2beb431e6fab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275857"
---
# <a name="linker-tools-error-lnk2020"></a>Błąd narzędzi konsolidatora LNK2020

nierozpoznany token "token"

Podobnie jak w przypadku niezdefiniowanego błędu zewnętrznego, z tą różnicą, że odwołanie jest realizowane za pośrednictwem metadanych. W metadanych należy zdefiniować wszystkie funkcje i dane.

Aby rozwiązać:

- Zdefiniuj brakującą funkcję lub dane lub

- Dołącz plik lub bibliotekę obiektu, w której jest już zdefiniowana brakująca funkcja lub dane.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje LNK2020.

```cpp
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

LNK2020 również będzie miała miejsce w przypadku utworzenia zmiennej typu szablonu zarządzanego, ale nie wystąpienia tego typu.

Poniższy przykład generuje LNK2020.

```cpp
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```
