---
description: 'Dowiedz się więcej o: błąd kompilatora C3279'
title: Błąd kompilatora C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: c257a97cad1603703e7dbf2ed0d9f5cb3e6134a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258021"
---
# <a name="compiler-error-c3279"></a>Błąd kompilatora C3279

częściowe i jawne specjalizacje oraz jawne wystąpienia szablonów klas zadeklarowanych w przestrzeni nazw CLI są niedozwolone

`cli`Przestrzeń nazw jest definiowana przez firmę Microsoft i zawiera pseudo Templates. Kompilator języka Microsoft C++ nie zezwala na zdefiniowane przez użytkownika, częściowe i jawne specjalizacje oraz jawne wystąpienia szablonów klas w tej przestrzeni nazw.

Poniższy przykład generuje C3279:

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
