---
description: 'Dowiedz się więcej o: znaki dwubajtowe'
title: Znaki dwubajtowe
ms.date: 11/04/2016
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
ms.openlocfilehash: 64b175402f98c1e687f453a897c8e240fd176e0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260829"
---
# <a name="wide-characters"></a>Znaki dwubajtowe

**3.1.3.4 ANSI** Wartość stałej znakowej liczby całkowitej, która zawiera więcej niż jeden znak lub stałą znakową, która zawiera więcej niż jeden znak wielobajtowy.

Zwykła stała znakowa, "AB" ma wartość całkowitą (int) 0x6162. W przypadku więcej niż jednego bajtu poprzednio odczytane bajty są przesunięte w lewo o wartość **CHAR_BIT** a następny bajt jest porównywany przy użyciu operatora bitowego lub z niską **CHAR_BIT** bitów. Liczba bajtów w stałej znakowej wielobajtowej nie może przekroczyć sizeof (int), która jest 4 dla kodu docelowego 32-bitowego.

Stała znaku wielobajtowego jest odczytywana jak powyżej i jest konwertowana na stałą o szerokim znaku przy użyciu `mbtowc` funkcji run-time. Jeśli wynik nie jest prawidłową stałą znaków dwubajtowych, zostanie wygenerowany błąd. W każdym przypadku liczba bajtów badanych przez `mbtowc` funkcję jest ograniczona do wartości `MB_CUR_MAX` .

## <a name="see-also"></a>Zobacz też

[Znaki](../c-language/characters.md)
