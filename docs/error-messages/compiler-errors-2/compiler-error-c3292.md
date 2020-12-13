---
description: 'Dowiedz się więcej o: błąd kompilatora C3292'
title: Błąd kompilatora C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 5c20ae5a03fd6eab442384c91c3357c2d9edb214
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144693"
---
# <a name="compiler-error-c3292"></a>Błąd kompilatora C3292

nie można ponownie otworzyć przestrzeni nazw interfejsu wiersza polecenia

Nie można zadeklarować przestrzeni nazw interfejsu wiersza polecenia w kodzie.  Aby uzyskać więcej informacji, zobacz [przestrzenie nazw platform, Default i CLI](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3292.

```cpp
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```
