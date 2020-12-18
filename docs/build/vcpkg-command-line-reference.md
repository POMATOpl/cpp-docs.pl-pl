---
title: vcpkg — dokumentacja wiersza polecenia
description: Dowiedz się, jak korzystać z opcji wiersza polecenia dla vcpkg w systemach Windows, macOS i Linux.
ms.date: 12/17/2020
ms.topic: reference
ms.technology: cpp-ide
ms.openlocfilehash: d60ebf983fea2eb41430f05b8c12e4a4a6fe370b
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684260"
---
# <a name="vcpkg-command-line-reference"></a>vcpkg — dokumentacja wiersza polecenia

Krótkie odwołanie do poleceń dostępnych w vcpkg.

## <a name="commands"></a>Polecenia

| Polecenie | Opis |
|--|--|
| **`vcpkg search [pat]`** | Wyszukaj pakiety dostępne do zainstalowania |
| **`vcpkg install <pkg>...`** | Instalowanie pakietu |
| **`vcpkg remove <pkg>...`** | Odinstalowywanie pakietu |
| **`vcpkg remove --outdated`** | Odinstaluj wszystkie nieaktualne pakiety |
| **`vcpkg list`** | Wyświetl listę zainstalowanych pakietów |
| **`vcpkg update`** | Wyświetl listę pakietów do zaktualizowania |
| **`vcpkg upgrade`** | Kompiluj ponownie wszystkie nieaktualne pakiety |
| **`vcpkg hash <file> [alg]`** | Mieszanie pliku przez określony algorytm, domyślny SHA512 |
| **`vcpkg integrate install`** | Udostępnienie zainstalowanych pakietów dla użytkownika. Wymaga uprawnień administratora przy pierwszym użyciu |
| **`vcpkg integrate remove`** | Usuń integrację na poziomie użytkownika |
| **`vcpkg integrate project`** | Generuj pakiet NuGet odwołującego się do użytku dla poszczególnych projektów programu VS |
| **`vcpkg export <pkg>... [opt]...`** | Eksportowanie pakietu |
| **`vcpkg edit <pkg>`** | Otwórz port do edycji (używa edytora%, domyślnego "Code") |
| **`vcpkg create <pkg> <url> [archivename]`** | Utwórz nowy pakiet |
| **`vcpkg cache`** | Wyświetlanie listy buforowanych pakietów |
| **`vcpkg version`** | Wyświetl informacje o wersji |
| **`vcpkg contact --survey`** | Wyświetlanie informacji kontaktowych w celu wysłania opinii. |

## <a name="options"></a>Opcje

| Opcja | Opis |
|--|--|
| **`--triplet <t>`** | Określ tryplet architektury docelowej. (domyślnie: `%VCPKG_DEFAULT_TRIPLET%` , zobacz również **`vcpkg help triplet`** ) |
| **`--vcpkg-root <path>`** | Określ katalog główny vcpkg (domyślnie: `%VCPKG_ROOT%` ) |

## <a name="see-also"></a>Zobacz także

[vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS](./vcpkg.md)\
[vcpkg w serwisie GitHub](https://github.com/Microsoft/vcpkg)\
[Zainstaluj vcpkg](install-vcpkg.md)\
[Integruj vcpkg](integrate-vcpkg.md)\
[Zarządzanie bibliotekami za pomocą vcpkg](manage-libraries-with-vcpkg.md)\
[Szybki Start](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Często zadawane pytania](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
