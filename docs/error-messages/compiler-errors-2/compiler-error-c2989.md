---
title: Błąd kompilatora C2989
ms.date: 11/04/2016
f1_keywords:
- C2989
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
ms.openlocfilehash: e5f03d644ab6c25b7eb0da0dc1684c7de5c2e6a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366137"
---
# <a name="compiler-error-c2989"></a>Błąd kompilatora C2989

"class": typ klasy została już zadeklarowana jako typ klasy korporacyjnej

Klasa ogólna lub szablonu redefiniuje nieszablonowe lub nieogólnej klasy. Sprawdź pliki nagłówkowe dla konfliktów.

Poniższy przykład spowoduje wygenerowanie C2989:

```cpp
// C2989.cpp
// compile with: /c
class C{};

template <class T>
class C{};  // C2989
class C2{};
```

C2989 może również wystąpić, gdy za pomocą typów ogólnych:

```cpp
// C2989b.cpp
// compile with: /clr /c
ref class GC1;

generic <typename T> ref class GC1;   // C2989
template <typename T> ref class GC2;

generic <typename T> ref class GC2;   // C2989
generic <typename T> ref class GCb;
template <typename T> ref class GC2;
generic <typename T> ref class GCc;
```