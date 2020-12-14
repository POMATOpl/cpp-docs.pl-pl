---
description: 'Dowiedz się więcej o: błąd kompilatora C3140'
title: Błąd kompilatora C3140
ms.date: 11/04/2016
f1_keywords:
- C3140
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
ms.openlocfilehash: d4655589c5901a0ba609bde0cb5cb96907e087c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304223"
---
# <a name="compiler-error-c3140"></a>Błąd kompilatora C3140

nie można mieć wielu atrybutów "module" w tej samej jednostce kompilacji

Atrybut [modułu](../../windows/attributes/module-cpp.md) można zdefiniować tylko raz dla każdego projektu.

Poniższy przykład generuje C3140:

```cpp
// C3140.cpp
// compile with: /c
[emitidl];
[module(name = "MyLibrary")];
[module(name = "MyLibrary2")];   // C3140
```
