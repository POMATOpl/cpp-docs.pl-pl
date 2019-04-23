---
title: Compiler Error C3469
ms.date: 11/04/2016
f1_keywords:
- C3469
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
ms.openlocfilehash: 1e935fb90c93d6f301226f3e9029c04929f179ac
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779076"
---
# <a name="compiler-error-c3469"></a>Compiler Error C3469

"type": nie można przesłać dalej klasy ogólnej

Przekazywanie dalej typu nie można użyć dla klasy generycznej.

Aby uzyskać więcej informacji, zobacz [Type Forwarding (C++sposób niezamierzony)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład tworzy składnik.

```
// C3469.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3466.

```
// C3469_b.cpp
// compile with: /clr /c
#using "C3469.dll"
[assembly:TypeForwardedTo(GR::typeid)];   // C3469
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```