---
description: 'Dowiedz się więcej o: błąd kompilatora C2731'
title: Błąd kompilatora C2731
ms.date: 11/04/2016
f1_keywords:
- C2731
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
ms.openlocfilehash: baae65ff1d09bafe37251b7593dc0d0c91c89f1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123308"
---
# <a name="compiler-error-c2731"></a>Błąd kompilatora C2731

"Identyfikator": funkcja nie może być przeciążona

Funkcje `main` , `WinMain` , `DllMain` i `LibMain` nie mogą być przeciążone.

Poniższy przykład generuje C2731:

```cpp
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```
