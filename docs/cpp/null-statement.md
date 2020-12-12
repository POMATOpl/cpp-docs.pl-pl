---
description: 'Dowiedz się więcej na temat: o wartości null'
title: Instrukcja o wartości Null
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 1aa488da395cf84ae9ef6d78939f1f1e3019c572
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146175"
---
# <a name="null-statement"></a>Instrukcja o wartości Null

"Instrukcja o wartości null" jest instrukcją wyrażenia z brakującym *wyrażeniem* . Jest przydatne, gdy składnia języka wywołuje instrukcję, ale nie ma oceny wyrażenia. Składa się z średnika.

Instrukcje o wartości null są często używane jako symbole zastępcze w instrukcjach iteracji lub jako instrukcje umieszczania etykiet na końcu złożonych instrukcji lub funkcji.

Poniższy fragment kodu przedstawia sposób kopiowania jednego ciągu do innego i zawiera instrukcję o wartości null:

```cpp
// null_statement.cpp
char *myStrCpy( char *Dest, const char *Source )
{
    char *DestStart = Dest;

    // Assign value pointed to by Source to
    // Dest until the end-of-string 0 is
    // encountered.
    while( *Dest++ = *Source++ )
        ;   // Null statement.

    return DestStart;
}

int main()
{
}
```

## <a name="see-also"></a>Zobacz też

[Instrukcja wyrażenia](../cpp/expression-statement.md)
