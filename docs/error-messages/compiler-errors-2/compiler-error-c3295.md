---
description: 'Dowiedz się więcej o: błąd kompilatora C3295'
title: Błąd kompilatora C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 55fab24088690f5d5bb92da0cc55442bcebeed01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144628"
---
# <a name="compiler-error-c3295"></a>Błąd kompilatora C3295

"#pragma pragma" może być używana tylko w zakresie globalnym lub przestrzeni nazw

Niektóre dyrektywy pragma nie mogą być używane w funkcji.  Aby uzyskać więcej informacji, zobacz [dyrektywy pragma i słowo kluczowe __pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3295.

```cpp
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```
