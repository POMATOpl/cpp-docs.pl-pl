---
description: Dowiedz się więcej na temat składni Filename-Parts
title: Składnia nazwy pliku-części
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 436481d52324b4c638b5fa0a9840ce0d9ef654f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192138"
---
# <a name="filename-parts-syntax"></a>Składnia nazwy pliku-części

Składnia nazwy pliku-części w poleceniach reprezentuje składniki pierwszego zależnej nazwy pliku (które mogą być zależne od założenia). Składniki nazwy pliku to dysk, ścieżka, nazwa podstawowa i rozszerzenie, które są określone, a nie na dysku. Użyj **% s** , aby reprezentować kompletną nazwę pliku. Użyj elementu **% &#124;**[*części*]**F** (pionowy znak kreski jest zgodny z symbolem procentu), aby reprezentować części nazwy pliku, gdzie *części* mogą mieć zero lub więcej z poniższych liter w dowolnej kolejności.

|Letter|Opis|
|------------|-----------------|
|Bez liter|Pełna nazwa (taka sama jak **% s**)|
|**d**|Dysk|
|**St**|Ścieżka|
|**n**|Nazwa podstawowa pliku|
|**adres**|Rozszerzenie pliku|

Na przykład jeśli nazwa pliku jest c:\prog.exe:

- % s zostanie c:\prog.exe

- % &#124;F zostanie c:\prog.exe

- % &#124;dF będzie c

- % &#124;pF zostanie c:\

- % &#124;fF będzie

- % &#124;Dr będzie exe

## <a name="see-also"></a>Zobacz też

[Polecenia w pliku reguł programu make](commands-in-a-makefile.md)
