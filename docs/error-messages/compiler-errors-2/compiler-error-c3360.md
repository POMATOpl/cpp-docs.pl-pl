---
title: Błąd kompilatora C3360 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3360
dev_langs:
- C++
helpviewer_keywords:
- C3360
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2ec9d43d9849e07010ac56989466c17ce37a93e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022867"
---
# <a name="compiler-error-c3360"></a>Błąd kompilatora C3360

"string": nie można utworzyć nazwy

Wartość, która została przekazana do [uuid](../../windows/uuid-cpp-attributes.md) atrybut nie jest prawidłowa.

Poniższy przykład spowoduje wygenerowanie C3360:

```
// C3360.cpp
[ uuid("1") ]
// try this line instead
// [ uuid("12341234-1234-1234-1234-123412341234") ]
struct A   // C3360
{
};

int main()
{
}
```