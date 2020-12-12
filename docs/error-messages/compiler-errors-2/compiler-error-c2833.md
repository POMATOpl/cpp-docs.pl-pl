---
description: 'Dowiedz się więcej o: błąd kompilatora C2833'
title: Błąd kompilatora C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: 3c1bd2cc60478dc5868c74d4bfeac1d7d3a4d9a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194491"
---
# <a name="compiler-error-c2833"></a>Błąd kompilatora C2833

> "operator *-name*" nie jest rozpoznanym operatorem lub typem

Po słowie **`operator`** musi następować *nazwa operatora* , który ma zostać przesłonięty, lub typ, który ma zostać przekształcony.

Aby uzyskać listę operatorów, które można zdefiniować w typie zarządzanym, zobacz [Operatory zdefiniowane przez użytkownika](../../dotnet/user-defined-operators-cpp-cli.md).

Poniższy przykład generuje C2833:

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
