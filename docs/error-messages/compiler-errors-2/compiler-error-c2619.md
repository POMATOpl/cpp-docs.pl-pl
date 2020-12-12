---
description: 'Dowiedz się więcej o: błąd kompilatora C2619'
title: Błąd kompilatora C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: 2ca9a8379901703299e89e71671ec0270c1ff1e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123552"
---
# <a name="compiler-error-c2619"></a>Błąd kompilatora C2619

"Identyfikator": statyczna składowa danych nie jest dozwolona w anonimowej strukturze lub Unii

Jest zadeklarowany element członkowski anonimowej struktury lub Unii **`static`** .

Poniższy przykład generuje C2619 i pokazuje, jak rozwiązać ten problem, usuwając słowo kluczowe static.

```cpp
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```
