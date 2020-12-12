---
description: 'Dowiedz się więcej o: ocenie tokenów'
title: Ocena tokenów
ms.date: 11/04/2016
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
ms.openlocfilehash: e22a904956b3f429585c6627a7fb2e8f8da6d222
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196532"
---
# <a name="evaluation-of-tokens"></a>Ocena tokenów

Gdy kompilator interpretuje tokeny, zawiera dowolną liczbę znaków w ramach jednego tokenu przed przejściem do następnego tokenu. Ze względu na to zachowanie kompilator może nie interpretować tokenów zgodnie z oczekiwaniami, jeśli nie są prawidłowo oddzielone znakami odstępu. Rozważ następujące wyrażenie:

```
i+++j
```

W tym przykładzie kompilator najpierw tworzy najdłuższy możliwy operator ( `++` ) od trzech znaków plus, a następnie przetwarza pozostałe znak plus jako operator dodawania ( `+` ). W tym celu wyrażenie jest interpretowane jako `(i++) + (j)` , nie `(i) + (++j)` . W tym i podobnym przypadku użyj białych znaków i nawiasów, aby uniknąć niejednoznaczności i zapewnić poprawne obliczanie wyrażeń.

**Specyficzne dla firmy Microsoft**

Kompilator języka C traktuje znak CTRL + Z jako wskaźnik końca pliku. Ignoruje dowolny tekst po kombinacji klawiszy CTRL + Z.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Tokeny języka C](../c-language/c-tokens.md)
