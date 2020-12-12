---
description: 'Dowiedz się więcej o: błąd kompilatora C2917'
title: Błąd kompilatora C2917
ms.date: 11/04/2016
f1_keywords:
- C2917
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
ms.openlocfilehash: c860ee47ae46db5667f39014b2f504f8f6d08e51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270436"
---
# <a name="compiler-error-c2917"></a>Błąd kompilatora C2917

"name": nieprawidłowy parametr szablonu

Lista parametrów szablonu zawiera identyfikator, który nie jest parametrem szablonu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2917.

```cpp
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```
