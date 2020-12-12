---
description: 'Dowiedz się więcej o: błąd kompilatora C2355'
title: Błąd kompilatora C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: f28799d4fbd72c7a5959bc4c68e1810b26052844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328371"
---
# <a name="compiler-error-c2355"></a>Błąd kompilatora C2355

"This": można odwoływać się tylko wewnątrz niestatycznych funkcji składowych lub niestatycznych inicjatorów składowych danych

**`this`** Wskaźnik jest prawidłowy tylko wewnątrz niestatycznych funkcji składowych lub niestatycznych inicjatorów składowych danych. Ten błąd może wynikać z tego, że zakres klasy definicji funkcji składowej poza deklaracją klasy nie jest prawidłowo kwalifikowany. Ten błąd może również wystąpić, gdy **`this`** wskaźnik jest używany w funkcji, która nie jest zadeklarowana w klasie.

Aby rozwiązać ten problem, upewnij się, że definicja funkcji składowej pasuje do deklaracji funkcji składowej w klasie i że nie jest ona zadeklarowana jako statyczna. W przypadku inicjatorów składowych danych upewnij się, że element członkowski danych nie jest zadeklarowany jako statyczny.

Poniższy przykład generuje C2355 i pokazuje, jak to naprawić:

```cpp
// C2355.cpp
// compile with: /c
class MyClass {};
MyClass *p = this;   // C2355

// OK
class MyClass2 {
public:
   void Test() {
      MyClass2 *p = this;
   }
};
```
