---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0033'
title: Błąd PRJ0033 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0033
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
ms.openlocfilehash: 7faf69cd9aaed6f90d9c546c4fc2383fd6808419
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241134"
---
# <a name="project-build-error-prj0033"></a>Błąd PRJ0033 kompilacji projektu

Właściwość "dodatkowe zależności" dla niestandardowego kroku kompilacji dla pliku "File" zawiera "Macro", który szacuje wartość "macro_expansion".

Niestandardowy krok kompilacji w pliku zawierał błąd w dodatkowej zależności prawdopodobnie z powodu problemu z oceną makra. Ten błąd może również oznaczać, że ścieżka jest źle sformułowana, zawierającą znaki lub kombinacje znaków, które nie są dozwolone w ścieżce pliku.

Aby rozwiązać ten problem, napraw makro lub Popraw specyfikację ścieżki. Szacowana ścieżka jest ścieżką bezwzględną z katalogu projektu.
