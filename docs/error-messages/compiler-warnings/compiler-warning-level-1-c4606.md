---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4606'
title: Ostrzeżenie kompilatora (poziom 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: b347be103d2a84dba2143861cb35b67f3d38fb9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341740"
---
# <a name="compiler-warning-level-1-c4606"></a>Ostrzeżenie kompilatora (poziom 1) C4606

\#Ostrzeżenie pragma: zignorowano element "warning_number"; Ostrzeżenia analizy kodu nie są skojarzone z poziomami ostrzeżeń

W przypadku ostrzeżeń dotyczących analizy kodu tylko, `error` `once` i `default` są obsługiwane za pomocą dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4606.

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
