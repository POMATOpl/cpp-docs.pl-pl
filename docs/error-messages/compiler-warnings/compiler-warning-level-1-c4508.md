---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4508'
title: Ostrzeżenie kompilatora (poziom 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: 4394f102c91934a949cdbbc82418d136187cbb7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294850"
---
# <a name="compiler-warning-level-1-c4508"></a>Ostrzeżenie kompilatora (poziom 1) C4508

"Function": funkcja powinna zwrócić wartość; Założono typ zwracany "void"

Nie określono zwracanego typu funkcji. W takim przypadku C4430 powinna również być wyzwalana, a kompilator implementuje poprawkę zgłoszoną przez C4430 (wartość domyślna to int).

Aby usunąć to ostrzeżenie, jawnie Zadeklaruj zwracany typ funkcji.

Poniższy przykład generuje C4508:

```cpp
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```
