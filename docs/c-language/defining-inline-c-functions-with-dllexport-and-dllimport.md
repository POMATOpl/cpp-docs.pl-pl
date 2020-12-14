---
description: 'Dowiedz się więcej o: definiowania wbudowanych funkcji języka C z dllexport i dllimport'
title: Definiowanie funkcji śródwierszowych języka C z dllexport i dllimport
ms.date: 11/04/2016
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
ms.openlocfilehash: 0ab176504b0fb75ca149ffa4b3a438960c22aad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186925"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Definiowanie funkcji śródwierszowych języka C z dllexport i dllimport

**Specyficzne dla firmy Microsoft**

Można zdefiniować jako wbudowaną funkcję z `dllexport` atrybutem. W takim przypadku funkcja jest zawsze tworzona i eksportowana, niezależnie od tego, czy żaden moduł w programie odwołuje się do funkcji. Założenie, że funkcja jest zaimportowana przez inny program.

Można również zdefiniować jako wbudowaną funkcję zadeklarowaną z **`dllimport`** atrybutem. W takim przypadku funkcja może być rozwinięta (podlega specyfikacji opcji kompilatora/Ob (inline), ale nigdy nie jest tworzona. W szczególności, jeśli jest wykonywana adres wbudowanej funkcji zaimportowanej, zwracany jest adres funkcji znajdującej się w pliku DLL. Takie zachowanie jest takie samo jak pobieranie adresu niewbudowanej funkcji zaimportowanej.

Statyczne dane lokalne i ciągi w funkcjach wbudowanych obsługują te same tożsamości między biblioteką DLL i klientem, tak jak w przypadku jednego programu (czyli pliku wykonywalnego bez interfejsu DLL).

Należy zachować ostrożność podczas udostępniania zaimportowanych funkcji wbudowanych. Na przykład w przypadku aktualizowania biblioteki DLL nie należy zakładać, że klient będzie używać zmienionej wersji biblioteki DLL. Aby upewnić się, że ładujesz poprawną wersję biblioteki DLL, ponownie skompiluj klienta biblioteki DLL.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje importowania i eksportowania biblioteki DLL](../c-language/dll-import-and-export-functions.md)
