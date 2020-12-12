---
description: 'Dowiedz się więcej o: błąd kompilatora C2913'
title: Błąd kompilatora C2913
ms.date: 11/04/2016
f1_keywords:
- C2913
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
ms.openlocfilehash: eba6a782c8ec9abe5c13e643d077c81d25d4bf2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270488"
---
# <a name="compiler-error-c2913"></a>Błąd kompilatora C2913

Jawna specjalizacja; Deklaracja nie jest specjalizacją szablonu klasy

Nie można specjalizacji klasy niebędącej szablonem.

Poniższy przykład generuje C2913:

```cpp
// C2913.cpp
// compile with: /c
class X{};
template <class T> class Y{};

template<> class X<int> {};   // C2913
template<> class Y<int> {};
```
