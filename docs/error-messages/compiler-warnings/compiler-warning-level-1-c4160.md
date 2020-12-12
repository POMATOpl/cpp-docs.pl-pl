---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4160'
title: Ostrzeżenie kompilatora (poziom 1) C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: afb9a0a30376a0e0b1c59b89e98a131ab5889017
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267199"
---
# <a name="compiler-warning-level-1-c4160"></a>Ostrzeżenie kompilatora (poziom 1) C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>pragma (pop,...): nie znaleziono wcześniej wypchnięcia identyfikatora "*Identifier*"

## <a name="remarks"></a>Uwagi

Instrukcja pragma w kodzie źródłowym próbuje wystawić identyfikator, który nie został wypchnięte. Aby uniknąć tego ostrzeżenia, należy się upewnić, że identyfikator zdjęte został prawidłowo wypchnięte.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4160 i pokazuje, jak go naprawić:

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```
