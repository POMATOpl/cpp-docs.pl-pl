---
description: 'Dowiedz się więcej o: błąd kompilatora C2085'
title: Błąd kompilatora C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 2cd828c9a18c06c5794bef01ba861f702af2e096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252119"
---
# <a name="compiler-error-c2085"></a>Błąd kompilatora C2085

"Identyfikator": nie należy do formalnej listy parametrów

Identyfikator został zadeklarowany w definicji funkcji, ale nie znajduje się na liście parametrów formalnych. (Tylko ANSI C)

Poniższy przykład generuje C2085:

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Możliwe rozwiązanie:

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

Gdy brakuje średnika, `func1()` wygląda jak definicja funkcji, a nie prototyp, więc `main` jest zdefiniowana w ramach `func1()` , generując błąd C2085 dla identyfikatora `main` .
