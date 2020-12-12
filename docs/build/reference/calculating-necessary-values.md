---
description: 'Dowiedz się więcej na temat: Obliczanie niezbędnych wartości'
title: Obliczanie niezbędnych wartości
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 92d8462be2db55dbc10375629b133d9286560878
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179346"
---
# <a name="calculating-necessary-values"></a>Obliczanie niezbędnych wartości

Dwie krytyczne elementy informacji muszą zostać obliczone przez procedurę pomocnika opóźnień. W tym celu istnieją dwie funkcje wbudowane w Delayhlp. cpp do obliczania tych informacji.

- Najpierw oblicza Indeks bieżącego importu w trzech różnych tabelach (tabela adresów importu (IAT), powiązanej tabeli adresów importowania (BIAT) i niepowiązanej tabeli adresów importu (UIAT)).

- Druga liczy liczbę importów w prawidłowym IAT.

```cpp
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="see-also"></a>Zobacz też

[Zrozumienie funkcji pomocnika](understanding-the-helper-function.md)
