---
description: 'Dowiedz się więcej na temat: Dokumentacja programu MSBuild dla projektów języka C++'
title: Dokumentacja programu MSBuild dla projektów C++ w programie Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 898757c8b7f1427c36e68a7227ec145abab8d078
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190617"
---
# <a name="msbuild-reference-for-c-projects"></a>Dokumentacja aparatu MSBuild dla projektów w języku C++

MSBuild to natywny system kompilacji dla wszystkich projektów w programie Visual Studio, w tym projekty języka C++. Podczas kompilowania projektu w zintegrowanym środowisku programistycznym (IDE) programu Visual Studio wywołuje narzędzie msbuild.exe, które z kolei wykorzystuje plik projektu. vcxproj i różne pliki targets i. props. Ogólnie rzecz biorąc zdecydowanie zalecamy użycie środowiska IDE programu Visual Studio do ustawiania właściwości projektu i wywoływać MSBuild. Ręczne edytowanie plików projektu może prowadzić do poważnych problemów, jeśli nie zostały prawidłowo wykonane.

Jeśli z jakiegoś powodu chcesz użyć programu MSBuild bezpośrednio z wiersza polecenia, zobacz [Korzystanie z programu MSBuild z poziomu wiersza polecenia](../msbuild-visual-cpp.md). Aby uzyskać więcej informacji na temat programu MSBuild, zobacz [MSBuild](/visualstudio/msbuild/msbuild) w dokumentacji programu Visual Studio.

## <a name="in-this-section"></a>W tej sekcji

[Funkcje wewnętrzne aparatu MSBuild dla projektów w języku C++](msbuild-visual-cpp-overview.md)<br/>
Informacje na temat sposobu przechowywania i używania właściwości i obiektów docelowych.

[Typowe makra dla właściwości i poleceń kompilacji](common-macros-for-build-commands-and-properties.md)<br/>
Opisuje makra (stałe czasu kompilacji), których można użyć do zdefiniowania właściwości, takich jak ścieżki i wersje produktów.

[Typy plików utworzone dla projektów C++](file-types-created-for-visual-cpp-projects.md)<br/>
Opisuje różne rodzaje plików, które program Visual Studio tworzy dla różnych typów projektów.

[Szablony projektów Visual Studio C++](visual-cpp-project-types.md)<br>
Zawiera opis typów projektów opartych na programie MSBuild, które są dostępne dla języka C++.

[Szablony nowych elementów w języku C++](using-visual-cpp-add-new-item-templates.md)<br>
Opisuje pliki źródłowe i inne elementy, które można dodać do projektu programu Visual Studio.

[Wstępnie skompilowane pliki nagłówkowe](../creating-precompiled-header-files.md) Jak używać prekompilowanych plików nagłówkowych i jak utworzyć własny niestandardowy kod wstępnie skompilowany w celu przyspieszenia czasu kompilacji.

[Odwołanie do właściwości projektu programu Visual Studio](property-pages-visual-cpp.md)<br/>
Dokumentacja referencyjna dla właściwości projektu ustawionych w środowisku IDE programu Visual Studio.

## <a name="see-also"></a>Zobacz też

[Odwołanie kompilacji C/C++](c-cpp-building-reference.md)
