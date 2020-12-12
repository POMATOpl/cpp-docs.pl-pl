---
description: 'Dowiedz się więcej o: BSCMAKE Reference'
title: Odwołanie BSCMAKE
ms.date: 05/06/2019
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 11a90561e22b9fb3a39f022ba188e5c9d155e45e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179432"
---
# <a name="bscmake-reference"></a>Odwołanie BSCMAKE

> [!WARNING]
> Mimo że usługa BSCMAKE jest nadal zainstalowana z programem Visual Studio, nie jest już używana przez IDE. Od programu Visual Studio 2008 informacje dotyczące przeglądania i symboli są przechowywane automatycznie w pliku SQL Server. sdf w folderze rozwiązania.

Narzędzie do konserwacji przeglądanych informacji firmy Microsoft (BSCMAKE.EXE) kompiluje plik informacji o przeglądaniu (BSC) z plików. sbr utworzonych podczas kompilacji. Niektóre narzędzia innych firm wykorzystują pliki BSC do analizy kodu.

Podczas kompilowania programu można automatycznie utworzyć plik informacji o przeglądaniu dla programu przy użyciu BSCMAKE do skompilowania pliku. Nie musisz wiedzieć, jak uruchomić program BSCMAKE, jeśli tworzysz plik informacji o przeglądaniu w środowisku deweloperskim programu Visual Studio. Warto jednak zapoznać się z tym tematem, aby poznać dostępne opcje.

Jeśli kompilujesz program poza środowiskiem programistycznym, można nadal utworzyć niestandardowy. bsc, który można przeanalizować w środowisku. Uruchom BSCMAKE na plikach SBR, które zostały utworzone podczas kompilacji.

> [!NOTE]
> To narzędzie można uruchomić tylko z poziomu wiersza polecenia programu Visual Studio Developer. Nie można uruchomić go z poziomu wiersza polecenia systemu lub Eksploratora plików.

Ta sekcja zawiera następujące tematy:

- [Kompilowanie plików informacji o przeglądaniu: Omówienie](building-browse-information-files-overview.md)

- [Kompilowanie pliku. bsc](building-a-dot-bsc-file.md)

- [Wiersz polecenia BSCMAKE](bscmake-command-line.md)

- [Plik polecenia BSCMAKE](bscmake-command-file-response-file.md)

- [Opcje BSCMAKE](bscmake-options.md)

- [Kody zakończenia BSCMAKE](bscmake-exit-codes.md)

## <a name="see-also"></a>Zobacz też

[Dodatkowe narzędzia do kompilacji MSVC](c-cpp-build-tools.md)
