---
description: 'Dowiedz się więcej o: błąd kompilatora C3113'
title: Błąd kompilatora C3113
ms.date: 11/04/2016
f1_keywords:
- C3113
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
ms.openlocfilehash: dcad27e26e0795b8d1901cca51dc5cd16a88ae5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115992"
---
# <a name="compiler-error-c3113"></a>Błąd kompilatora C3113

"Structure" nie może być szablonem/ogólnym

Podjęto próbę wykonania szablonu klasy lub klasy ogólnej poza interfejsem lub wyliczeniem.

Poniższy przykład generuje C3113:

```cpp
// C3113.cpp
// compile with: /c
template <class T>
enum E {};   // C3113
// try the following line instead
// class MyClass{};
```
