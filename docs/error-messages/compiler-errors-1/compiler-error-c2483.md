---
description: 'Dowiedz się więcej o: błąd kompilatora C2483'
title: Błąd kompilatora C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 5edafbbb0852eb622f34698421ce9a2b794f9209
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123880"
---
# <a name="compiler-error-c2483"></a>Błąd kompilatora C2483

>"*Identyfikator*": obiekt z konstruktorem lub destruktorem nie może być zadeklarowany jako "Thread"

Ten komunikat o błędzie jest przestarzały w programie Visual Studio 2015 i nowszych wersjach. W poprzednich wersjach zmienne zadeklarowane z `thread` atrybutem nie mogą być inicjowane za pomocą konstruktora lub innego wyrażenia, które wymaga oceny czasu wykonywania. Do zainicjowania danych jest wymagane wyrażenie statyczne `thread` .

## <a name="example"></a>Przykład

Poniższy przykład generuje C2483 w Visual Studio 2013 i wcześniejszych wersjach.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>Zobacz też

[wątek](../../cpp/thread.md)
