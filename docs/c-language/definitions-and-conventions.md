---
description: 'Dowiedz się więcej na temat: definicje i konwencje'
title: Definicje i konwencje
ms.date: 11/04/2016
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
ms.openlocfilehash: 892f14bfc3059406bbc192640e04c0181d06eee2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186873"
---
# <a name="definitions-and-conventions"></a>Definicje i konwencje

Terminale są punktami końcowymi w definicji składni. Inne rozwiązanie nie jest możliwe. Terminale obejmują zestaw słów zarezerwowanych i identyfikatorów zdefiniowanych przez użytkownika.

Nieterminale są symbolami zastępczymi w składni i są zdefiniowane w innym miejscu w tym podsumowaniu składni. Definicje mogą być cykliczne.

Opcjonalny składnik jest wskazywany przez <sub>wybór</sub>z indeksu. Przykład:

>  *wyrażenie*{<sub>opt</sub> **}**

wskazuje opcjonalne wyrażenie ujęte w nawiasy klamrowe.

Konwencje składni używają różnych atrybutów czcionki dla różnych składników składni. Symbole i czcionki są następujące:

|Atrybut|Opis|
|---------------|-----------------|
|*nieterminal*|Typ kursywy oznacza nieterminale.|
|**`const`**|Terminale w pogrubieniu są literałami zarezerwowanymi i symbolami, które muszą zostać wprowadzone jako pokazane. Znaki w tym kontekście zawsze uwzględniają wielkość liter.|
|<sub>uszlachetniania</sub>|Nieterminale, po których następuje <sub>wybór</sub> , są zawsze opcjonalne.|
|domyślny krój czcionki|Znaki w zestawie opisany lub wymieniony w tym kroju pisma mogą być używane jako terminale w instrukcjach języka C.|

Jest to dwukropek (**:**) po wprowadzeniu definicji przez nieterminala. Definicje alternatywne są wyświetlane w oddzielnych wierszach, z wyjątkiem przypadków, gdy są poprzedzone wyrazami "one of".

## <a name="see-also"></a>Zobacz też

[Podsumowanie składni języka C](../c-language/c-language-syntax-summary.md)
