---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4211'
title: Ostrzeżenie kompilatora (poziom 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: bbd6469dc98d95342538bf3a9065b4647619d69a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314740"
---
# <a name="compiler-warning-level-4-c4211"></a>Ostrzeżenie kompilatora (poziom 4) C4211

użyto niestandardowego rozszerzenia: ponownie zdefiniowano extern jako static

Przy użyciu domyślnych rozszerzeń Microsoft (/ze) można ponownie zdefiniować **`extern`** Identyfikator jako **`static`** .

## <a name="example"></a>Przykład

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

Takie ponowne definicje są nieprawidłowe pod kątem zgodności ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).
