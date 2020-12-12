---
description: 'Dowiedz się więcej o: 32-bitowym formacie daty/godziny systemu Windows'
title: 32-bitowe formaty Time-Date systemu Windows
ms.date: 11/04/2016
f1_keywords:
- vc.time
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
ms.openlocfilehash: 3893a2abc5d00cfba7ec83209470e907f87d3e94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135788"
---
# <a name="32-bit-windows-timedate-formats"></a>32-bitowe formaty daty/godziny systemu Windows

Czas pliku i Data są przechowywane pojedynczo, przy użyciu liczb całkowitych bez znaku jako pól bitowych. Data i godzina pliku są pakowane w następujący sposób:

### <a name="time"></a>Czas

|Pozycja bitowa:|0 1 2 3 4|5 6 7 8 9 A|B C D E F|
|-------------------|-----------------------|---------------------------|-----------------------|
|Długość|5|6|5|
|Zawartość:|godziny|minutes|2-sekundowe przyrosty|
|Zakres wartości:|0-23|0-59|0-29 w 2-sekundowych odstępach czasu|

### <a name="date"></a>Date

|Pozycja bitowa:|0 1 2 3 4 5 6|7 8 9 A|B C D E F|
|-------------------|-------------------------------|-------------------|-----------------------|
|Długość|7|4|5|
|Zawartość:|rok|miesiąc|dzień|
|Zakres wartości:|0-119|1-12|1-31|
||(względem 1980)|||

## <a name="see-also"></a>Zobacz też

[Stałe globalne](../c-runtime-library/global-constants.md)
