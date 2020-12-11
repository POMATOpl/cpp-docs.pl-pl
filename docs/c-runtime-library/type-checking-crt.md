---
description: 'Dowiedz się więcej na temat: sprawdzanie typu (CRT)'
title: Sprawdzać typ (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.types
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
ms.openlocfilehash: cf27847bf2aeef278fb4699cea5a0cf74a961086
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162356"
---
# <a name="type-checking-crt"></a>Sprawdzać typ (CRT)

Kompilator wykonuje ograniczone sprawdzanie typów funkcji, które mogą przyjmować zmienną liczbę argumentów w następujący sposób:

|Wywołanie funkcji|Argumenty zaznaczone przez typ|
|-------------------|-----------------------------|
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Pierwszy argument (ciąg formatu)|
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Pierwsze dwa argumenty (plik lub bufor i ciąg formatu)|
|`_snprintf_s`|Pierwsze trzy argumenty (plik lub bufor, liczba i ciąg formatu)|
|`_open`|Pierwsze dwa argumenty (ścieżka i `_open` Flaga)|
|`_sopen_s`|Pierwsze trzy argumenty (ścieżka, `_open` Flaga i tryb udostępniania)|
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Pierwsze dwa argumenty (wskaźnik ścieżki i pierwszego argumentu)|
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Pierwsze trzy argumenty (flaga trybu, ścieżka i pierwszy argument wskaźnika)|

Kompilator wykonuje te same ograniczone typy kontroli dla odpowiedników szerokich znaków tych funkcji.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki CRT](../c-runtime-library/crt-library-features.md)
