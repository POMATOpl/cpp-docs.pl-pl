---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4269'
title: Ostrzeżenie kompilatora (poziom 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 6b00eeee4a831ee7876556838f03d4b74f4790fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266133"
---
# <a name="compiler-warning-level-1-c4269"></a>Ostrzeżenie kompilatora (poziom 1) C4269

"Identyfikator": "const" automatyczne dane zainicjowane przy użyciu domyślnego konstruktora wygenerowanego przez kompilator produkuje niezawodne wyniki

**`const`** Automatyczne wystąpienie klasy nieuproszczonej jest inicjowane za pomocą domyślnego konstruktora wygenerowanego przez kompilator.

## <a name="example"></a>Przykład

```cpp
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

Ponieważ to wystąpienie klasy jest generowane na stosie, początkowa wartość `m_data` może być dowolna. Ponadto, ponieważ jest to **`const`** wystąpienie, wartość `m_data` nie może być nigdy zmieniana.
