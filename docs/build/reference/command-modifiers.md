---
description: 'Dowiedz się więcej o: Modyfikatory poleceń'
title: Modyfikatory poleceń
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
ms.openlocfilehash: d17d5f25719dfe5638ca6688105517d385bdf68e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182375"
---
# <a name="command-modifiers"></a>Modyfikatory poleceń

Można określić jeden lub więcej modyfikatorów poleceń poprzedzających polecenie, opcjonalnie oddzielone spacjami lub tabulatorami. Podobnie jak w przypadku poleceń Modyfikatory muszą mieć wcięcia.

|Modyfikator|Przeznaczenie|
|--------------|-------------|
|\@*dotyczące*|Zapobiega wyświetlaniu polecenia. Polecenia Display by nie są pomijane. Domyślnie NMAKE ECHA wszystkie wykonane polecenia. Użyj/S, aby pominąć wyświetlanie dla całego pliku reguł programu make; Użyj **. DYSKRETNy** , aby pominąć wyświetlanie dla części pliku reguł programu make.|
|**-**\[*Liczba*] *polecenie*|Wyłącza sprawdzanie błędów dla *polecenia*. Domyślnie NMAKE zatrzymuje się, gdy polecenie zwraca kod zakończenia różny od zera. Jeśli jest używana *wartość-Number* , NMAKE przestaje działać, jeśli kod zakończenia przekroczy *liczbę*. Spacje lub znaki tabulacji nie mogą występować między kreską i *cyfrą.* Między `number` i *poleceniem* musi znajdować się co najmniej jedno miejsce lub karta. Użyj/I, aby wyłączyć sprawdzanie błędów dla całego pliku reguł programu make; Użyj **. Ignoruj** , aby wyłączyć sprawdzanie błędów dla części pliku reguł programu make.|
|**!** *dotyczące*|Wykonuje *polecenie* dla każdego pliku zależnego, jeśli używa *polecenia* <strong>$\*\*</strong> (wszystkie pliki zależne w zależności) lub **$?** (wszystkie pliki zależne w zależności od późniejszej sygnatury czasowej).|

## <a name="see-also"></a>Zobacz też

[Polecenia w pliku reguł programu make](commands-in-a-makefile.md)
