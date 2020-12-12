---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4272'
title: Ostrzeżenie kompilatora (poziom 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: a44e3a4121c1d01b15af47b0b4eefb1f982423bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266120"
---
# <a name="compiler-warning-level-1-c4272"></a>Ostrzeżenie kompilatora (poziom 1) C4272

"Function": jest oznaczona __declspec (dllimport); podczas importowania funkcji należy określić natywną konwencję wywoływania.

Wystąpił błąd podczas eksportowania funkcji oznaczonej konwencją wywoływania [__clrcall](../../cpp/clrcall.md) i kompilator generuje to ostrzeżenie, jeśli próbujesz zaimportować funkcję oznaczoną jako `__clrcall` .

Poniższy przykład generuje C4272:

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
