---
description: 'Dowiedz się więcej o: dyrektywy dot'
title: Dyrektywy Dot
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
ms.openlocfilehash: 41b13d5f0f0f0a04ee47a9958be76c384617fe5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192866"
---
# <a name="dot-directives"></a>Dyrektywy Dot

Określ dyrektywy dot poza blokiem opisu na początku wiersza. Dyrektywy dot zaczynają się kropką (. ) i następuje dwukropek (:). Dozwolone są spacje i karty. Nazwy dyrektywy dot są rozróżniane wielkości liter i są pisane wielką literą.

|Dyrektywę|Przeznaczenie|
|---------------|-------------|
|**. Ignoruj**|Ignoruje niezerowe kody zakończenia zwracane przez polecenia, od miejsca, w którym jest określony na końcu pliku reguł programu make. Domyślnie NMAKE zatrzymuje się, gdy polecenie zwróci kod zakończenia różny od zera. Aby przywrócić sprawdzanie błędów, użyj **! CMDSWITCHES**. Aby zignorować kod zakończenia pojedynczego polecenia, należy użyć modyfikatora kreska (-). Aby zignorować kody zakończenia dla całego pliku, użyj/I.|
|**. SZLACHETNe:** *cele*|Zachowuje *elementy docelowe* na dysku, jeśli polecenia aktualizacji są zatrzymane; nie ma wpływu, jeśli polecenie obsługuje przerwanie przez usunięcie pliku. Rozdziel nazwy docelowe z co najmniej jedną spacją lub tabulatorami. Domyślnie NMAKE usuwa element docelowy, jeśli kompilacja została przerwana przez naciśnięcie klawiszy CTRL + C lub CTRL + BREAK. Każde użycie **. CENNy** odnosi się do całego pliku reguł programu make; wiele specyfikacji jest skumulowanych.|
|**. AUTOMATYCZNIE**|Pomija wyświetlanie wykonanych poleceń, w miejscu, na końcu pliku reguł programu make. Domyślnie NMAKE wyświetla polecenia, które wywołuje. Aby przywrócić echo, użyj **! CMDSWITCHES**. Aby pominąć echo jednego polecenia, należy użyć **@** modyfikatora. Aby pominąć echo dla całego pliku, użyj/S.|
|**. SUFIKSy:**`list`|Wyświetla listę rozszerzeń do wnioskowania o dopasowanie reguły; wstępnie zdefiniowane w celu uwzględnienia następujących rozszerzeń:. exe. obj. asm. c. cpp. cxx. bas. cbl. for. pas. res. rc. f. F90|

Aby zmienić **.** Kolejność na liście sufiksów lub aby określić nową listę, Wyczyść listę i określ nowe ustawienie. Aby wyczyścić listę, określ brak rozszerzeń po dwukropku:

```
.SUFFIXES :
```

Aby dodać dodatkowe sufiksy na końcu listy, określ

```
.SUFFIXES : suffixlist
```

gdzie *suffixlist* jest listą dodatkowych sufiksów, oddzielonych co najmniej jedną spacją lub tabulatorami. Aby wyświetlić bieżące ustawienie **. SUFIKSy**, uruchom NMAKE z/P.

## <a name="see-also"></a>Zobacz też

[Odwołanie NMAKE](nmake-reference.md)
