---
description: 'Dowiedz się więcej o: błąd kompilatora C2388'
title: Błąd kompilatora C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 63a2758b4e214b38c7d999bdc2a33d328709ea67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123984"
---
# <a name="compiler-error-c2388"></a>Błąd kompilatora C2388

"symbol": symbol nie może być zadeklarowany zarówno jako __declspec (AppDomain), jak i \_ _declspec (Process)

`appdomain` `process` **`__declspec`** Modyfikatory i nie mogą być używane dla tego samego symbolu. Magazyn dla zmiennej istnieje dla procesu lub dla domeny aplikacji.

Aby uzyskać więcej informacji, zobacz temat [AppDomain](../../cpp/appdomain.md) i [Process](../../cpp/process.md).

Poniższy przykład generuje C2388:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
