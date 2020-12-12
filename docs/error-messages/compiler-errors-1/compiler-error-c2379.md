---
description: 'Dowiedz się więcej o: błąd kompilatora C2379'
title: Błąd kompilatora C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 4b278040107a026ffd5f7bee79e709519647cb54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174718"
---
# <a name="compiler-error-c2379"></a>Błąd kompilatora C2379

formalny numer parametru ma inny typ podczas podwyższania poziomu

Typ określonego parametru jest niezgodny, za pomocą domyślnej promocji, z typem w poprzedniej deklaracji. Jest to błąd w języku ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) i ostrzeżenie z rozszerzeniami firmy Microsoft (**/ze**).

Poniższy przykład generuje C2379:

```c
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
