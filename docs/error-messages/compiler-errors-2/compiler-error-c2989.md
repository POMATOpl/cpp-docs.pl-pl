---
title: Błąd kompilatora C2989 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2989
dev_langs:
- C++
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79da071b592a31ea3fe7ca486a7e02abc770f08e
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890094"
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