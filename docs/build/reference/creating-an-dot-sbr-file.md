---
description: 'Dowiedz się więcej o programie: Tworzenie. Plik SBR'
title: Tworzenie pliku .Sbr
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 7f3e056418fe1716dc0130330b09c369e9bdceff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196922"
---
# <a name="creating-an-sbr-file"></a>Tworzenie pliku .Sbr

> [!WARNING]
> Mimo że usługa BSCMAKE jest nadal zainstalowana z programem Visual Studio, nie jest już używana przez IDE. Od programu Visual Studio 2008 informacje dotyczące przeglądania i symboli są przechowywane automatycznie w pliku SQL Server. sdf w folderze rozwiązania.

Pliki wejściowe dla BSCMAKE są plikami SBR. Kompilator tworzy plik. sbr dla każdego pliku obiektu (. obj), który kompiluje. Podczas kompilowania lub aktualizowania pliku informacji o przeglądaniu wszystkie pliki. sbr projektu muszą być dostępne na dysku.

Aby utworzyć plik. sbr ze wszystkimi możliwymi informacjami, określ [/fr](fr-fr-create-dot-sbr-file.md).

Aby utworzyć plik. sbr, który nie zawiera lokalnych symboli, określ [/fr](fr-fr-create-dot-sbr-file.md). Jeśli pliki. sbr zawierają symbole lokalne, można je pominąć z pliku. bsc przy użyciu [opcji/El](bscmake-options.md) BSCMAKE`.`

Można utworzyć plik. sbr bez wykonywania pełnej kompilacji. Na przykład można określić opcję/ZS kompilatora, aby przeprowadzić sprawdzanie składni i nadal generować plik. sbr, jeśli określono/FR lub/fr.

Proces kompilacji może być bardziej wydajny, jeśli pliki. SBR są po raz pierwszy spakowane w celu usunięcia definicji, do których nie istnieją odwołania. Kompilator automatycznie pakuje pliki SBR.

## <a name="see-also"></a>Zobacz też

[Kompilowanie. Plik BSC](building-a-dot-bsc-file.md)
