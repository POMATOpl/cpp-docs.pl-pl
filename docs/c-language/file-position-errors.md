---
description: 'Dowiedz się więcej o: Błędy położenia plików'
title: Błędy pozycji w pliku
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: d29f8d86280427db915c016fea0fd80567913baf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196155"
---
# <a name="file-position-errors"></a>Błędy pozycji w pliku

**4.9.9.1 ANSI, 4.9.9.4** Wartość, dla której makro `errno` jest ustawiane przez `fgetpos` funkcję lub `ftell` w przypadku niepowodzenia

Gdy `fgetpos` lub `ftell` Niepowodzenie, `errno` jest ustawiona na stałą manifestu, `EINVAL` Jeśli pozycja jest nieprawidłowa lub `EBADF` Jeśli numer pliku jest nieodpowiedni. Stałe są zdefiniowane w ERRNO. H.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)
