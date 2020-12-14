---
description: 'Dowiedz się więcej o: błąd kompilatora C3638'
title: Błąd kompilatora C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 1d1cc59cd8065a5b0e661292b717ba885c6febeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239197"
---
# <a name="compiler-error-c3638"></a>Błąd kompilatora C3638

"operator": nie można ponownie zdefiniować odpakowania standardowego i rozpakowywania operatorów konwersji

Kompilator definiuje operator konwersji dla każdej zarządzanej klasy do obsługi niejawnego opakowania. Nie można ponownie zdefiniować tego operatora.

Aby uzyskać więcej informacji, zobacz [niejawny opakowanie](../../extensions/boxing-cpp-component-extensions.md).

Poniższy przykład generuje C3638:

```cpp
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```
