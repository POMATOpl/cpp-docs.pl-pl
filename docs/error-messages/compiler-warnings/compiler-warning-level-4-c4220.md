---
title: Kompilator ostrzeżenie (poziom 4) C4220 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4220
dev_langs:
- C++
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70c6b104c924a09570d4bd77191f1df715726370
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118781"
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