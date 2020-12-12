---
description: 'Dowiedz się więcej na temat: stałe atrybutów pliku'
title: Stałe atrybutów pliku
ms.date: 11/04/2016
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
ms.openlocfilehash: 8b57549b4a21cc5d699f933009c575b3f3fca81d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306368"
---
# <a name="file-attribute-constants"></a>Stałe atrybutów pliku

## <a name="syntax"></a>Składnia

```
#include <io.h>
```

## <a name="remarks"></a>Uwagi

Te stałe określają bieżące atrybuty pliku lub katalogu określonego przez funkcję.

Atrybuty są reprezentowane przez następujące stałe manifestu:

|Stała|Opis|
|-|-|
|`_A_ARCH`| Folderu. Ustawiaj za każdym razem, gdy plik zostanie zmieniony, i wyczyszczony przez polecenie BACKUP. Wartość: 0x20|
|`_A_HIDDEN`| Ukryty plik. Zwykle niewidoczny dla polecenia DIR, chyba że jest używana opcja/AH. Zwraca informacje o normalnych plikach oraz plikach z tym atrybutem. Wartość: 0x02|
|`_A_NORMAL`| Typow. Plik może być odczytywany lub zapisywana bez ograniczeń. Wartość: 0x00|
|`_A_RDONLY`| Tylko do odczytu. Nie można otworzyć pliku do zapisu i nie można utworzyć pliku o tej samej nazwie. Wartość: 0x01|
|`_A_SUBDIR`| Podkatalogu. Wartość: 0x10|
|`_A_SYSTEM`| Plik systemowy. Zwykle niewidoczny dla polecenia DIR, chyba że jest używana opcja/AS. Wartość: 0x04|

Wiele stałych można łączyć z operatorem OR (&#124;).

## <a name="see-also"></a>Zobacz też

[Funkcje wyszukiwania nazw plików](../c-runtime-library/filename-search-functions.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
