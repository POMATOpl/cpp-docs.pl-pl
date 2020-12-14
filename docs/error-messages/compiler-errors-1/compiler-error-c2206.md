---
description: 'Dowiedz się więcej o: błąd kompilatora C2206'
title: Błąd kompilatora C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: 53a4c6e25d7864db9a2c69b7e57e0c73e7a80a28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245710"
---
# <a name="compiler-error-c2206"></a>Błąd kompilatora C2206

"Function": typedef nie można używać do definicji funkcji

A służy **`typedef`** do definiowania typu funkcji.

Poniższy przykład generuje C2206:

```cpp
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```
