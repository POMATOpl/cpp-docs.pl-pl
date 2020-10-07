---
title: Ostrzeżenie kompilatora (poziom 3) C4316
description: Opis ostrzeżenia kompilatora języka C++ C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 3cb512aa9b851f3b3b26f7a50854a4d887087e81
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806563"
---
# <a name="compiler-warning-level-3-c4316"></a>Ostrzeżenie kompilatora (poziom 3) C4316

Obiekt przydzielony na stercie może nie być wyrównany dla tego typu.

Obiekt z nadmiernym wyrównaniem przydzielony przy użyciu `operator new` może nie mieć określonego wyrównania. Zastąp [operator new](../../c-runtime-library/new-operator-crt.md) i [operator delete](../../c-runtime-library/delete-operator-crt.md) dla niewyrównanych typów, tak aby korzystały z wyrównanych procedur alokacji, na przykład [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) i [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Poniższy przykład generuje C4316:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```
