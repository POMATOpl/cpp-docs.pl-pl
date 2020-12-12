---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4926'
title: Ostrzeżenie kompilatora (poziom 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: 9b4f1d86085a5e0560237378728c2f267c44c780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301896"
---
# <a name="compiler-warning-level-1-c4926"></a>Ostrzeżenie kompilatora (poziom 1) C4926

"Identyfikator": symbol jest już zdefiniowany: atrybuty zostały zignorowane

Znaleziono deklarację do przodu, ale konstrukcja o tej samej nazwie już istnieje. Atrybuty deklaracji Forward są ignorowane.

Poniższy przykład generuje C4926:

```cpp
// C4926.cpp
// compile with: /W1
[module(name="MyLib")];

[coclass]
struct a {
};

[coclass]
struct a;   // C4926

int main() {
}
```
