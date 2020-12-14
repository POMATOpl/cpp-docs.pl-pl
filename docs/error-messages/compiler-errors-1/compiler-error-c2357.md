---
description: 'Dowiedz się więcej o: błąd kompilatora C2357'
title: Błąd kompilatora C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: a58317fc4706d6385d3753a434c8e4fd80dc79b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276741"
---
# <a name="compiler-error-c2357"></a>Błąd kompilatora C2357

"Identyfikator": musi być funkcją typu "Type"

Kod deklaruje wersję `atexit` funkcji, która nie jest zgodna z wersją zadeklarowaną wewnętrznie przez kompilator. Zadeklaruj `atexit` w następujący sposób:

```
int __cdecl atexit(void (__cdecl *)());
```

Aby uzyskać więcej informacji, zobacz [init_seg](../../preprocessor/init-seg.md).

Poniższy przykład generuje C2357:

```cpp
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```
