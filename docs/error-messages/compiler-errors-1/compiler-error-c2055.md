---
description: 'Dowiedz się więcej o: błąd kompilatora C2055'
title: Błąd kompilatora C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 0692488b8e1ea91fe235ade512c5fbe5094cdaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174939"
---
# <a name="compiler-error-c2055"></a>Błąd kompilatora C2055

Oczekiwano formalnej listy parametrów, a nie listy typów

Definicja funkcji zawiera listę typów parametrów zamiast formalnej listy parametrów. ANSI C wymaga, aby parametry formalne były nazwane, chyba że są puste lub wielokropek ( `...` ).

Poniższy przykład generuje C2055:

```c
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```
