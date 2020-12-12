---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4228'
title: Ostrzeżenie kompilatora (poziom 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: efb247d64ced8c44e84b8f3cfb4e15705eb57b1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266354"
---
# <a name="compiler-warning-level-1-c4228"></a>Ostrzeżenie kompilatora (poziom 1) C4228

użyto niestandardowego rozszerzenia: kwalifikatory po przecinku na liście deklaratorów są ignorowane

Użycie kwalifikatorów, takich jak **`const`** lub **`volatile`** po przecinku, podczas deklarowania zmiennych jest rozszerzeniem Microsoft ([/ze](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Przykład

```cpp
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```
