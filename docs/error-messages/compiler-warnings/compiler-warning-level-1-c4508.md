---
title: Kompilator ostrzeżenie (poziom 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: c96db3d4bd1124c96b22363531b7739d0757b613
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160812"
---
# <a name="compiler-warning-level-1-c4508"></a>Kompilator ostrzeżenie (poziom 1) C4508

'Funkcja': funkcja powinna zwrócić wartość; Założono typ zwracany "void"

Funkcja nie ma zwracanego określonego typu. W tym przypadku C4430 powinien również wyzwalać i kompilator implementuje rozwiązać zgłaszane przez C4430 (wartość domyślna to int).

Aby rozwiązać tego ostrzeżenia, należy jawnie deklarować typ zwracany funkcji.

Poniższy przykład spowoduje wygenerowanie C4508:

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```