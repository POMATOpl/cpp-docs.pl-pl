---
description: 'Dowiedz się więcej o: błąd kompilatora C2142'
title: Błąd kompilatora C2142
ms.date: 11/04/2016
f1_keywords:
- C2142
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
ms.openlocfilehash: 65bd189fe99bb54549e458b093b72d8e47b840a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235531"
---
# <a name="compiler-error-c2142"></a>Błąd kompilatora C2142

Deklaracje funkcji różnią się, parametry zmiennej określone tylko w jednej z nich

Jedna deklaracja funkcji zawiera listę parametrów zmiennych. Inna deklaracja nie jest. Tylko ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)).

Poniższy przykład generuje C2142:

```c
// C2142.c
// compile with: /Za /c
void func();
void func( int, ... );   // C2142
void func2( int, ... );   // OK
```
