---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4202'
title: Ostrzeżenie kompilatora (poziom 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: 56abe76d623605460d76bfacb69a128c05762931
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173262"
---
# <a name="compiler-warning-level-4-c4202"></a>Ostrzeżenie kompilatora (poziom 4) C4202

użyto niestandardowego rozszerzenia: "...": parametr prototypu w liście nazw jest niedozwolony

Definicja funkcji starego stylu zawiera argumenty zmiennych. Te definicje generują błędy pod kątem zgodności ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Przykład

```c
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```
