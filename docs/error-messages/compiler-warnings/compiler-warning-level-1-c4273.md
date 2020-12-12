---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4273'
title: Ostrzeżenie kompilatora (poziom 1) C4273
ms.date: 11/04/2016
f1_keywords:
- C4273
helpviewer_keywords:
- C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
ms.openlocfilehash: a7b36d8154f5f97a9497b79a91b2684fbad0d677
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266029"
---
# <a name="compiler-warning-level-1-c4273"></a>Ostrzeżenie kompilatora (poziom 1) C4273

"Function": niespójne powiązanie biblioteki DLL

Dwie definicje w pliku różnią się w zależności od użycia elementu [dllimport](../../cpp/dllexport-dllimport.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C4273.

```cpp
// C4273.cpp
// compile with: /W1 /c
char __declspec(dllimport) c;
char c;   // C4273, delete this line or the line above to resolve
```

Poniższy przykład generuje C4273.

```cpp
// C4273_b.cpp
// compile with: /W1 /clr /c
#include <stdio.h>
extern "C" int printf_s(const char *, ...);   // C4273
```
