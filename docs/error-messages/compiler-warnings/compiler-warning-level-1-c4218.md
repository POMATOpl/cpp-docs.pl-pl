---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4218'
title: Ostrzeżenie kompilatora (poziom 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 76fc53a5b290a55c73fe036e2fc02b7a1afedd23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266419"
---
# <a name="compiler-warning-level-1-c4218"></a>Ostrzeżenie kompilatora (poziom 1) C4218

użyto niestandardowego rozszerzenia: należy określić co najmniej klasę magazynu lub typ

Przy użyciu domyślnych rozszerzeń Microsoft (/ze) można zadeklarować zmienną bez określania typu lub klasy magazynu. Domyślnym typem jest **`int`** .

## <a name="example"></a>Przykład

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Takie deklaracje są nieprawidłowe pod kątem zgodności ze standardem ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).
