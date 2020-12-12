---
description: Dowiedz się więcej na temat przechowywania i wyrównania struktur
title: Magazynowanie i wyrównanie struktur
ms.date: 11/04/2016
helpviewer_keywords:
- alignment of structures
- structure storage
- storing structures
- packing structures
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
ms.openlocfilehash: 8cffc3ddfcc868a7ccb727a5092e2389dbf016a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213692"
---
# <a name="storage-and-alignment-of-structures"></a>Magazynowanie i wyrównanie struktur

**Specyficzne dla firmy Microsoft**

Elementy członkowskie struktur są przechowywane sekwencyjnie, w kolejności, w której były zadeklarowane: pierwszy element członkowski ma najniższy adres pamięci, a ostatni element członkowski – najwyższy.

Każdy obiekt danych ma *wymaganie wyrównania*. W przypadku struktur, wymagany jest największy z ich elementów członkowskich. Każdy obiekt ma przydzieloną *przesunięcie* , aby

*przesunięcie* `%` *wyrównanie — wymaganie* `==` 2,0

Sąsiadujące pola bitowe są pakowane w takie same 1-, 2- lub 4-bajtowe jednostki alokacji, jeśli typy całkowite mają taki sam rozmiar i jeśli następne pole bitowe pasuje do bieżącej jednostki alokacji bez przekraczania granicy nałożonej przez wspólne wymagania wyrównania pól bitowych.

Aby zaoszczędzić miejsce lub zachować zgodność z istniejącymi strukturami danych, możesz chcieć przechowywać struktury w mniej lub bardziej kompaktowy sposób. Opcja kompilatora [/ZP](../build/reference/zp-struct-member-alignment.md)[*n*] i [pakiet #pragma](../preprocessor/pack.md) sterują sposobem, w jaki dane struktury są zapakowane do pamięci. W przypadku użycia opcji/ZP [*n*], gdzie *n* to 1, 2, 4, 8 lub 16, każdy element członkowski struktury po pierwszym jest przechowywany w granicach bajtów, które są wymaganymi wyrównaniami pola lub rozmiarem pakowania (*n*), w zależności od tego, który jest mniejszy. Wyrażone jako formuła, granice bajtowe są

```
min( n, sizeof( item ) )
```

gdzie *n* to rozmiar pakowania wyrażony za pomocą opcji/ZP [*n*], a *element* jest elementem członkowskim struktury. Domyślny rozmiar pakowania to /Zp8.

Aby użyć dyrektywy `pack` do określenia pakowania innego, niż określone w wierszu polecenia dla określonej struktury, przed strukturą podaj dyrektywę `pack`, gdzie rozmiar pakowania wynosi 1, 2, 4, 8 lub 16. Aby przywrócić pakowanie podane w wierszu polecenia, określ dyrektywę `pack` bez argumentów.

Pola bitowe są domyślnie rozmiarem **`long`** kompilatora języka Microsoft C. Elementy członkowskie struktury są wyrównane do rozmiaru typu lub rozmiaru/ZP [*n*], w zależności od tego, który jest mniejszy. Domyślny rozmiar to 4.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Deklaracje struktury](../c-language/structure-declarations.md)
