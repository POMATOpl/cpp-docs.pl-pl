---
description: 'Dowiedz się więcej o programie: testowanie znaków'
title: Testowanie znaków
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: b7d73bce671787622814e11d8f3add7a1092572a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190539"
---
# <a name="character-testing"></a>Testowanie znaków

**ANSI 4.3.1** Zestawy znaków testowane przez,,,, `isalnum` , `isalpha` `iscntrl` `islower` `isprint` i `isupper` funkcje

Na poniższej liście opisano te funkcje, które są implementowane przez kompilator języka Microsoft C.

|Funkcja|Testy dla|
|--------------|---------------|
|`isalnum`|Znaki 0-9, A-Z, a-z ASCII 48-57, 65-90, 97-122|
|`isalpha`|Znaki A-Z, a-z ASCII 65-90, 97-122|
|`iscntrl`|ASCII 0 -31, 127|
|`islower`|Znaki a-z ASCII 97-122|
|`isprint`|Znaki A-Z, a-z, 0-9, interpunkcja, spacja ASCII 32-126|
|`isupper`|Znaki A-Z ASCII 65-90|

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)
