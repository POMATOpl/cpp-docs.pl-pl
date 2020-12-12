---
description: 'Dowiedz się więcej o: Instrukcje iteracji (C++)'
title: Instrukcje iteracji (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
ms.openlocfilehash: 71edf526ed641a5bcd7944c546486cf3d2fb5059
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190292"
---
# <a name="iteration-statements-c"></a>Instrukcje iteracji (C++)

Instrukcje iteracji powodują, że instrukcje (lub złożone instrukcje), które mają być wykonywane zero lub więcej razy, podlegają pewnym kryteriom zakończenia pętli. Kiedy te instrukcje są instrukcjami złożonymi, są wykonywane w kolejności, z wyjątkiem przypadków, gdy napotkana jest instrukcja [Break](../cpp/break-statement-cpp.md) lub [Continue](../cpp/continue-statement-cpp.md) .

C++ zawiera cztery instrukcje iteracji — [while](../cpp/while-statement-cpp.md), [do](../cpp/do-while-statement-cpp.md), [dla](../cpp/for-statement-cpp.md)i z [zakresu dla](../cpp/range-based-for-statement-cpp.md). Każda z tych iteracji wykonuje iteracje do momentu, gdy jego wyrażenie zakończenia zwróci wartość zero (false) lub dopóki zakończenie pętli jest wymuszane za pomocą **`break`** instrukcji. Poniższa tabela zawiera podsumowanie tych instrukcji i ich działań; Każdy z nich został szczegółowo omówiony w poniższych sekcjach.

### <a name="iteration-statements"></a>Instrukcje iteracji

|Instrukcja|Oceniane na|Inicjalizacja|Przyrost|
|---------------|------------------|--------------------|---------------|
|**`while`**|Góra pętli|Nie|Nie|
|**`do`**|Dolna pętla|Nie|Nie|
|**`for`**|Góra pętli|Tak|Tak|
|**oparte na zakresie dla**|Góra pętli|Tak|Tak|

Część instrukcji instrukcji iteracji nie może być deklaracją. Jednak może to być złożonej instrukcji zawierającej deklarację.

## <a name="see-also"></a>Zobacz też

[Omówienie instrukcji języka C++](../cpp/overview-of-cpp-statements.md)
