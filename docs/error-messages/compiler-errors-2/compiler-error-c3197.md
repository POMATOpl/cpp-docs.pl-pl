---
title: Błąd kompilatora C3197
ms.date: 11/04/2016
f1_keywords:
- C3197
helpviewer_keywords:
- C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
ms.openlocfilehash: 1519daf906485f78fe155d0f67e63d8e8e97ae29
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739223"
---
# <a name="compiler-error-c3197"></a>Błąd kompilatora C3197

słowo kluczowe ": może być używane tylko w definicjach

W deklaracji użyto słowa kluczowego, ale jest ono prawidłowe tylko w definicji.

Poniższy przykład generuje C3197:

```cpp
// C3197.cpp
// compile with: /clr /c
ref struct R abstract;   // C3197
ref struct R abstract {};   // OK

public ref class MyObject;   // C3197
ref class MyObject;   // OK
public ref class MyObject {};   // OK
```
