---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0034'
title: Błąd PRJ0034 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0034
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
ms.openlocfilehash: a5eb76b5a11cfed0789f6f5e5aca52e8215f4c5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241069"
---
# <a name="project-build-error-prj0034"></a>Błąd PRJ0034 kompilacji projektu

Właściwość "dodatkowe zależności" dla niestandardowego kroku kompilacji na poziomie projektu zawiera "makro", które oblicza wartość "macro_expansion".

Niestandardowy krok kompilacji w projekcie zawiera błąd w dodatkowej zależności prawdopodobnie z powodu problemu z oceną makra. Ten błąd może również oznaczać, że ścieżka jest źle sformułowana, zawierającą znaki lub kombinacje znaków, które nie są dozwolone w ścieżce pliku.

Aby rozwiązać ten problem, napraw makro lub Popraw specyfikację ścieżki. Szacowana ścieżka jest ścieżką bezwzględną z katalogu projektu.
