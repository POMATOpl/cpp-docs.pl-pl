---
description: 'Dowiedz się więcej o: definiowania wbudowanych funkcji języka C++ z dllexport i dllimport'
title: Definiowanie funkcji śródwierszowych języka C++ z dllexport i dllimport
ms.date: 11/04/2016
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
ms.openlocfilehash: 158fc5a8fa3805763b1a5abc731abc8905310a27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339478"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Definiowanie funkcji śródwierszowych języka C++ z dllexport i dllimport

**Specyficzne dla firmy Microsoft**

Można zdefiniować jako wbudowaną funkcję z **`dllexport`** atrybutem. W takim przypadku funkcja jest zawsze tworzona i eksportowana, niezależnie od tego, czy żaden moduł w programie odwołuje się do funkcji. Założenie, że funkcja jest zaimportowana przez inny program.

Można również zdefiniować jako wbudowaną funkcję zadeklarowaną z **`dllimport`** atrybutem. W takim przypadku funkcja może być rozwinięta (z zastrzeżeniem specyfikacji/OB), ale nigdy nie jest tworzona. W szczególności, jeśli jest wykonywana adres wbudowanej funkcji zaimportowanej, zwracany jest adres funkcji znajdującej się w pliku DLL. Takie zachowanie jest takie samo jak pobieranie adresu niewbudowanej funkcji zaimportowanej.

Te reguły mają zastosowanie do funkcji wbudowanych, których definicje pojawiają się w definicji klasy. Ponadto statyczne dane lokalne i ciągi w funkcjach wbudowanych zachowują te same tożsamości między biblioteką DLL i klientem, tak jak w przypadku pojedynczego programu (to jest plik wykonywalny bez interfejsu DLL).

Należy zachować ostrożność podczas udostępniania zaimportowanych funkcji wbudowanych. Na przykład w przypadku aktualizowania biblioteki DLL nie należy zakładać, że klient będzie używać zmienionej wersji biblioteki DLL. Aby upewnić się, że ładujesz poprawną wersję biblioteki DLL, ponownie skompiluj klienta biblioteki DLL.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
