---
title: Ostrzeżenie kompilatora (poziom 1) C4068
ms.date: 11/04/2016
f1_keywords:
- C4068
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
ms.openlocfilehash: ba6e57fb954e0331e8eede5e7859fbeed5ce6424
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626931"
---
# <a name="compiler-warning-level-1-c4068"></a>Ostrzeżenie kompilatora (poziom 1) C4068

nieznana pragma

Kompilator zignorował nierozpoznaną wartość [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md). Upewnij się, że **pragma** jest dozwolona przez używany kompilator. Poniższy przykład generuje C4068:

```cpp
// C4068.cpp
// compile with: /W1
#pragma NotAValidPragmaName   // C4068, use valid name to resolve
int main()
{
}
```