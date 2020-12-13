---
description: 'Dowiedz się więcej o: błąd kompilatora C2868'
title: Błąd kompilatora C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: c6a6368fbdfe61014a606fadce92322234e438f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333788"
---
# <a name="compiler-error-c2868"></a>Błąd kompilatora C2868

> "*Identyfikator*": niedozwolona składnia dla deklaracji using; Oczekiwano kwalifikowanej nazwy

[Deklaracja using](../../cpp/using-declaration.md) wymaga *nazwy kwalifikowanej*, `::` oddzielonej sekwencji operator zakresu () nazwy przestrzeni nazw, klasy lub wyliczenia kończącej się nazwą identyfikatora. Aby wprowadzić nazwę z globalnej przestrzeni nazw, można użyć operatora rozpoznawania pojedynczego zakresu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2868, a także wyświetla poprawne użycie:

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```
