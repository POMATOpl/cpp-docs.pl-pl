---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0032'
title: Błąd PRJ0032 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0032
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
ms.openlocfilehash: 25c8f9480e63a8afee23c880912e17632111a4c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241147"
---
# <a name="project-build-error-prj0032"></a>Błąd PRJ0032 kompilacji projektu

Właściwość "Outputs" niestandardowego kroku kompilacji na poziomie projektu zawiera "makro", które oblicza wartość "macro_expansion".

Niestandardowy krok kompilacji w projekcie miał prawdopodobnie nieprawidłowe wyniki wyjściowe z powodu problemu z oceną makra. Ten błąd może również oznaczać, że ścieżka jest źle sformułowana, zawierającą znaki lub kombinacje znaków, które nie są dozwolone w ścieżce pliku.

Aby rozwiązać ten problem, napraw makro lub Popraw specyfikację ścieżki. Szacowana ścieżka jest ścieżką bezwzględną z katalogu projektu.
