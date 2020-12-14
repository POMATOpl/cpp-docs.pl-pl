---
description: 'Dowiedz się więcej o: błąd kompilatora C3462'
title: Błąd kompilatora C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: e201dc9d999438053d5fd8d70813360c28a534df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315793"
---
# <a name="compiler-error-c3462"></a>Błąd kompilatora C3462

"Type": tylko typ importowany może być przekazywany

Atrybut TypeForwardedTo musi zostać zastosowany do typu w metadanych, do którego się odwołuje.

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Przykłady

Poniższy przykład tworzy składnik.

```cpp
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

Poniższy przykład generuje C3462.

```cpp
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```
