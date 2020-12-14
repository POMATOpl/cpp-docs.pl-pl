---
description: 'Dowiedz się więcej o: błąd kompilatora C3669'
title: Błąd kompilatora C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: b746c64af06178caf1006417f61c5f1e853cb67d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228953"
---
# <a name="compiler-error-c3669"></a>Błąd kompilatora C3669

"member": specyfikator przesłonięcia "override" nie jest dozwolony na statycznych funkcjach składowych lub konstruktorach

Nieprawidłowe przesłonięcie. Aby uzyskać więcej informacji, zobacz [jawne zastąpienia](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3669.

```cpp
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```
