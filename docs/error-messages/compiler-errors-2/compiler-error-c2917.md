---
title: Błąd kompilatora C2917
ms.date: 11/04/2016
f1_keywords:
- C2917
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
ms.openlocfilehash: 6926d96eccadacd427cc4d13b93db494809c3775
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406785"
---
# <a name="compiler-error-c2917"></a>Błąd kompilatora C2917

"name": nieprawidłowy parametr szablonu

Lista parametrów szablonu zawiera identyfikator, który nie jest parametrem szablonu.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2917.

```
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```