---
description: 'Dowiedz się więcej na temat: dopełnianie i wyrównywanie elementów członkowskich struktury'
title: Wypełnienie i wyrównanie struktur członkowskich
ms.date: 10/18/2018
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
ms.openlocfilehash: db2530ecb00e5a01f5d10ff45da55420a8139be0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137452"
---
# <a name="padding-and-alignment-of-structure-members"></a>Wypełnienie i wyrównanie struktur członkowskich

**3.5.2.1 ANSI** Uzupełnienie i wyrównanie elementów członkowskich struktur oraz tego, czy pole bitowe może obsłużyć granicę jednostki magazynu

Elementy członkowskie struktur są przechowywane sekwencyjnie, w kolejności, w której były zadeklarowane: pierwszy element członkowski ma najniższy adres pamięci, a ostatni element członkowski – najwyższy.

Każdy obiekt danych ma wymaganie wyrównania. Wyrównanie — wymaganie dla wszystkich danych z wyjątkiem struktur, Unii i tablic jest rozmiarem obiektu lub bieżącym rozmiarem pakowania (określonym przy użyciu/ZP lub `pack` pragma, w zależności od tego, co jest mniejsze). W przypadku struktur, Unii i tablic, dopasowanie-wymaganie jest największym wymaganiem dla elementów członkowskich. Każdy obiekt ma przydzieloną przesunięcie, aby

*przesunięcie* **%** *wyrównanie — wymagania* **= = 0**

Sąsiadujące pola bitowe są pakowane w takie same 1-, 2- lub 4-bajtowe jednostki alokacji, jeśli typy całkowite mają taki sam rozmiar i jeśli następne pole bitowe pasuje do bieżącej jednostki alokacji bez przekraczania granicy nałożonej przez wspólne wymagania wyrównania pól bitowych.

## <a name="see-also"></a>Zobacz też

[Struktury, złożenia, wyliczenia i pola bitowe](../c-language/structures-unions-enumerations-and-bit-fields.md)
