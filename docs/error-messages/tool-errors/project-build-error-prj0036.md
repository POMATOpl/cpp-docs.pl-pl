---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0036'
title: Błąd PRJ0036 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0036
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
ms.openlocfilehash: 753c526d7d15a0d90bef71b7923a4353ed02b098
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240965"
---
# <a name="project-build-error-prj0036"></a>Błąd PRJ0036 kompilacji projektu

Właściwość "dodatkowe pliki" narzędzia Web Deployment zawierała nieprawidłowy wpis.

Właściwość dodatkowe pliki na stronie właściwości wdrożenia sieci Web zawiera błąd, prawdopodobnie z powodu problemu z oceną makra. Ten błąd może również oznaczać, że ścieżka jest źle sformułowana, zawierającą znaki lub kombinacje znaków, które nie są dozwolone w ścieżce pliku.

Aby rozwiązać ten problem, napraw makro lub Popraw specyfikację ścieżki. Szacowana ścieżka jest ścieżką bezwzględną z katalogu projektu.

Ten błąd może również oznaczać, że jeden z plików, do którego się odwołuje, nie istnieje.
