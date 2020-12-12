---
description: 'Dowiedz się więcej o: błąd kompilatora C3076'
title: Błąd kompilatora C3076
ms.date: 11/04/2016
f1_keywords:
- C3076
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
ms.openlocfilehash: 27fbfe27d2e8efb1abee611701fdbde8f0d3d09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320183"
---
# <a name="compiler-error-c3076"></a>Błąd kompilatora C3076

"wystąpienie": nie można osadzić wystąpienia typu referencyjnego "Type" w typie natywnym

Typ natywny nie może zawierać wystąpienia typu CLR.

Aby uzyskać więcej informacji, zobacz [semantyka stosu języka C++ dla typów referencyjnych](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3076.

```cpp
// C3076.cpp
// compile with: /clr /c
ref struct U {};

struct V {
   U y;   // C3076
};

ref struct W {
   U y;   // OK
};
```
