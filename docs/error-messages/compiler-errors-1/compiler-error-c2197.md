---
description: 'Dowiedz się więcej o: błąd kompilatora C2197'
title: Błąd kompilatora C2197
ms.date: 11/04/2016
f1_keywords:
- C2197
helpviewer_keywords:
- C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
ms.openlocfilehash: a82a39eba23cae617cf910101f5550fd0f9f0ad4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341922"
---
# <a name="compiler-error-c2197"></a>Błąd kompilatora C2197

"Function": zbyt wiele argumentów dla wywołania

Kompilator wykrył zbyt wiele parametrów dla wywołania funkcji lub nieprawidłowej deklaracji funkcji.

Poniższy przykład generuje C2197:

```c
// C2197.c
// compile with: /Za /c
void func( int );
int main() {
   func( 1, 2 );   // C2197 two actual parameters
   func( 2 );   // OK
}
```
