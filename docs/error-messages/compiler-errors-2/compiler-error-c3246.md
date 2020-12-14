---
description: 'Dowiedz się więcej o: błąd kompilatora C3246'
title: Błąd kompilatora C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: 5a74b642abe2e184e8e505ec1000433357de2522
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307198"
---
# <a name="compiler-error-c3246"></a>Błąd kompilatora C3246

"Class": nie można dziedziczyć po elemencie "Type", ponieważ został zadeklarowany jako "Sealed"

Klasa oznaczona jako [zapieczętowana](../../extensions/sealed-cpp-component-extensions.md) nie może być klasą bazową dla żadnych innych klas.

Poniższy przykład generuje C3246:

```cpp
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
