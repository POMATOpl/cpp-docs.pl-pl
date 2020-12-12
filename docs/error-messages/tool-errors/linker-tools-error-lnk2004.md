---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2004'
title: Błąd narzędzi konsolidatora LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 6fc08f343726e6b037c33e9eef53d3fbac8f176f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338518"
---
# <a name="linker-tools-error-lnk2004"></a>Błąd narzędzi konsolidatora LNK2004

przepełnienie naprawy względem elementu GP do "target"; krótka sekcja "sekcja" jest za duża lub poza zakresem.

Sekcja jest za duża.

Aby rozwiązać ten problem, zmniejsz rozmiar krótkiej sekcji, jawnie umieszczając dane w długich sekcjach za pośrednictwem #pragma sekcji (". SectionName", odczytu, zapisu, Long) i korzystania `__declspec(allocate(".sectionname"))` z definicji i deklaracji danych.  Przykład:

```
#pragma section(".data$mylong", read, write, long)
__declspec(allocate(".data$mylong"))
char    rg0[1] = { 1 };
char    rg1[2] = { 1 };
char    rg2[4] = { 1 };
char    rg3[8] = { 1 };
char    rg4[16] = { 1 };
char    rg5[32] = { 1 };
```

Można również przenieść logicznie pogrupowane dane do własnej struktury, która będzie kolekcją danych większą niż 8 bajtów, które kompilator przydzieli w jednolongowej sekcji danych.  Przykład:

```
// from this...
int     w1  = 23;
int     w2 = 46;
int     w3 = 23*3;
int     w4 = 23*4;

// to this...
struct X {
    int     w1;
    int     w2;
    int     w3;
    int     w4;
} x  = { 23, 23*2, 23*3, 23*4 };
```

Ten błąd występuje po błędzie krytycznym `LNK1165` .
