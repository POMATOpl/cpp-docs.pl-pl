---
title: Kompilator ostrzeżenie (poziom 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: 177fb01ba4181f72740724d107fe08e6680ed492
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542444"
---
# <a name="compiler-warning-level-4-c4220"></a>Kompilator ostrzeżenie (poziom 4) C4220

pozostałe parametry dopasowań VarArgs

W obszarze domyślna rozszerzenia Microsoft (/Ze) wskaźnik do funkcji pasuje do wskaźnika do funkcji z podobnym, lecz zmienne, argumenty.

## <a name="example"></a>Przykład

```
// C4220.c
// compile with: /W4

int ( *pFunc1) ( int a, ... );
int ( *pFunc2) ( int a, int b);

int main()
{
   if ( pFunc1 != pFunc2 ) {};  // C4220
}
```

Takie wskaźniki nie są zgodne w obszarze zgodności ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).