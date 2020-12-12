---
description: 'Dowiedz się więcej o: błąd kompilatora C3467'
title: Błąd kompilatora C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: c00c78852380537d744c8d01681a921e487826df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113444"
---
# <a name="compiler-error-c3467"></a>Błąd kompilatora C3467

"Type": ten typ został już przekazany

Kompilator znalazł więcej niż jedną deklarację typu forward dla tego samego typu. Dozwolona jest tylko jedna deklaracja na typ.

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Przykłady

Poniższy przykład tworzy składnik.

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

Poniższy przykład generuje C3467.

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
