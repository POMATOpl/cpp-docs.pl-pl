---
description: Dowiedz się więcej na temat poleceń w pliku reguł programu make
title: Polecenia w pliku reguł programu Make
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: a4f3c6d3cc9b5d567548d7b3f2bd7679d492ebf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179086"
---
# <a name="commands-in-a-makefile"></a>Polecenia w pliku reguł programu Make

Reguła blokowania lub wnioskowania opisu określa blok poleceń do uruchomienia, jeśli zależność jest nieaktualna. NMAKE wyświetla każde polecenie przed uruchomieniem, chyba że/S, **. DYSKRETNy**, **! CMDSWITCHES** lub \@ jest używany. NMAKE szuka zgodnej reguły wnioskowania, jeśli blok opisu nie następuje po bloku poleceń.

Blok poleceń zawiera jeden lub więcej poleceń, każdy w osobnym wierszu. Między zależnością lub regułą i blokiem poleceń nie może być pusty wiersz. Jednak może być wyświetlany wiersz zawierający tylko spacje lub tabulatory; Ten wiersz jest interpretowany jako polecenie o wartości null i nie wystąpił żaden błąd. W wierszach polecenia są dozwolone puste wiersze.

Wiersz polecenia rozpoczyna się od co najmniej jednej spacji lub tabulatorów. Ukośnik odwrotny (\), po którym następuje znak nowego wiersza, jest interpretowany jako spacja w poleceniu; Użyj ukośnika odwrotnego na końcu wiersza, aby kontynuować polecenie w następnym wierszu. NMAKE interpretuje ukośnik odwrotny, jeśli jakikolwiek inny znak, łącznie z spacją lub tabulatorem, następuje po ukośniku odwrotnym.

Polecenie poprzedzone średnikiem (;) może występować w wierszu zależności lub w regule wnioskowania, niezależnie od tego, czy polecenia bloku poleceń są następujące:

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

[Modyfikatory poleceń](command-modifiers.md)

[Składnia nazwy pliku-części](filename-parts-syntax.md)

[Pliki wbudowane w pliku reguł programu make](inline-files-in-a-makefile.md)

## <a name="see-also"></a>Zobacz też

[Odwołanie NMAKE](nmake-reference.md)
