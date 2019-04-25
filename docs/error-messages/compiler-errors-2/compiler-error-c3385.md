---
title: Błąd kompilatora C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: 0cf8f75588339420c688db6e808a62a9fb0ac15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328773"
---
# <a name="compiler-error-c3385"></a>Błąd kompilatora C3385

"class::function": funkcja, która ma atrybut niestandardowy DllImport nie może zwrócić wystąpienia klasy

Zdefiniowane jako znajdujące się w pliku .dll określony za pomocą funkcji `DllImport` atrybutu nie może zwrócić wystąpienia klasy.

Poniższy przykład spowoduje wygenerowanie C3385:

```
// C3385.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

struct SomeStruct1 {};

public ref struct Wrap {
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385
};
```
