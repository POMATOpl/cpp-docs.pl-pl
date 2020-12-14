---
description: 'Dowiedz się więcej na temat: makra filename'
title: Makra nazwy pliku
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
ms.openlocfilehash: 2b10d021d27eedf008a143472715ee8e0cbecde5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200575"
---
# <a name="filename-macros"></a>Makra nazwy pliku

Makra filename są wstępnie zdefiniowane jako nazwy plików określone w zależności (niepełna Specyfikacja nazw plików na dysku). Te makra nie muszą być ujęte w nawiasy, gdy są wywoływane; Określ tylko znak $, jak pokazano.

|Makro|Znaczenie|
|-----------|-------------|
|**$\@**|Pełna nazwa elementu docelowego (ścieżka, nazwa podstawowa, rozszerzenie), zgodnie z aktualną nazwą.|
|**$$\@**|Pełna nazwa elementu docelowego (ścieżka, nazwa podstawowa, rozszerzenie), zgodnie z aktualną nazwą. Prawidłowe tylko jako zależne w zależności.|
|**$&#42;**|Ścieżka bieżącego elementu docelowego i nazwa podstawowa pomniejszona o rozszerzenie pliku.|
|**$&#42;&#42;**|Wszystkie zależności od bieżącego elementu docelowego.|
|**$?**|Wszystkie elementy zależne z późniejszą sygnaturą czasową niż bieżący element docelowy.|
|**$<**|Plik zależny z późniejszą sygnaturą czasową niż bieżący element docelowy. Prawidłowy tylko w poleceniach w regułach wnioskowania.|

Aby określić część wstępnie zdefiniowanego makra filename, Dołącz modyfikator makra i umieść zmodyfikowane makro w nawiasach.

|Modyfikator|Wynikająca część nazwy pliku|
|--------------|-----------------------------|
|**Wykres**|Dysk Plus — katalog|
|**B**|Nazwa podstawowa|
|**N**|Nazwa podstawowa plus rozszerzenie|
|**R**|Dysk Plus katalog Plus nazwa podstawowa|

## <a name="see-also"></a>Zobacz też

[Specjalne makra NMAKE](special-nmake-macros.md)
