---
title: UNIX
description: Wskazówki dotyczące przenoszenia programu do systemu UNIX.
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- unix
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
ms.openlocfilehash: 3975db2407943b329fa7eded0d72d63524428210
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765214"
---
# <a name="unix"></a>UNIX

Jeśli planujesz porty programów do systemu UNIX, postępuj zgodnie z następującymi wskazówkami:

- Nie usuwaj plików nagłówkowych z podkatalogu SYS. Pliki nagłówków SYS można umieścić w innym miejscu tylko wtedy, gdy nie planujesz transportowania programów do systemu UNIX.

- Użyj ogranicznika Path zgodnego z systemem UNIX w procedurach, które przyjmują ciągi reprezentujące ścieżki i nazwy plików jako argumenty. W tym celu system UNIX obsługuje tylko ukośnik (/), ale systemy operacyjne Win32 obsługują zarówno ukośnik odwrotny ( \\ ), jak i ukośnik (/). W tej dokumentacji są stosowane ukośniki zgodne z systemem UNIX jako ograniczniki ścieżek w `#include` instrukcjach. Jednakże powłoka poleceń systemu operacyjnego Windows CMD.EXE, nie obsługuje ukośnika w poleceniach wprowadzonych w wierszu polecenia.)

- Należy używać ścieżek i nazw plików, które działają poprawnie w systemie UNIX, w których jest rozróżniana wielkość liter. W systemie plików tabeli alokacji plików (FAT) w systemach operacyjnych Win32 nie jest rozróżniana wielkość liter. System plików NTFS zachowuje przypadek dla list katalogów, ale ignoruje wielkość liter podczas wyszukiwania plików i innych operacji systemu.

> [!NOTE]
> W tej wersji Visual C++ informacje o zgodności z systemem UNIX zostały usunięte z opisów funkcji.

## <a name="see-also"></a>Zobacz też

[Zgodność](../c-runtime-library/compatibility.md)
