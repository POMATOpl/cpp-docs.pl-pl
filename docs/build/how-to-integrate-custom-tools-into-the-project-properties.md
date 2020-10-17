---
title: 'Porady: integrowanie narzędzi niestandardowych we właściwościach projektu'
description: Jak zintegrować niestandardowe narzędzia we właściwościach projektu w projektach Visual Studio C++.
ms.date: 10/08/2020
helpviewer_keywords:
- 'MSBuild (C++), howto: integrate custom tools'
ms.openlocfilehash: 4b88bf94a92efaf5046fd83e5c6358f3fdf80895
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099670"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Porady: integrowanie narzędzi niestandardowych we właściwościach projektu

Możesz dodać niestandardowe opcje narzędzia do okna **stron właściwości** programu Visual Studio, tworząc plik XML.

W sekcji **Właściwości konfiguracji** okna **strony właściwości** są wyświetlane grupy ustawień znane jako *reguły*. Każda reguła zawiera ustawienia dla narzędzia lub grupy funkcji. Na przykład reguła **konsolidatora** zawiera ustawienia dla narzędzia konsolidatora. Ustawienia w regule mogą być podzielone na *Kategorie*.

Można utworzyć plik reguły, który zawiera właściwości niestandardowego narzędzia, dzięki czemu właściwości są ładowane podczas uruchamiania programu Visual Studio. Aby uzyskać informacje na temat sposobu modyfikowania pliku, zobacz [rozszerzalność platformy część 2](/archive/blogs/vsproject/platform-extensibility-part-2) w blogu zespołu projektu programu Visual Studio.

::: moniker range="vs-2015"

Folder, w którym ma zostać umieszczony plik reguły, zależy od ustawień regionalnych i używanej wersji programu Visual Studio. W wierszu polecenia programu Visual Studio 2015 lub starszej, folder Rules ma wartość *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>`* . `<version>`Wartość jest *`v140`* w programie Visual Studio 2015. `<locale>`Jest to identyfikator LCID, na przykład `1033` w języku angielskim. Użyjesz innej ścieżki dla każdej wersji programu Visual Studio, która jest zainstalowana, i dla każdego języka. Na przykład domyślna ścieżka folderu dla programu Visual Studio 2015 Community Edition w języku angielskim może być taka sama *`C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\v140\1033\`* .

::: moniker-end

::: moniker range="vs-2017"

Folder, w którym ma zostać umieszczony plik reguły, zależy od ustawień regionalnych i używanej wersji programu Visual Studio. W wierszu polecenia programu Visual Studio 2017 Developer znajduje się folder reguły *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . `<locale>`Jest to identyfikator LCID, na przykład `1033` w języku angielskim. W wierszu polecenia programu Visual Studio 2015 lub starszej, folder reguł to *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* , gdzie `<version>` wartość jest *`v140`* w programie Visual Studio 2015. Użyjesz innej ścieżki dla każdej wersji programu Visual Studio, która jest zainstalowana, i dla każdego języka. Na przykład domyślna ścieżka folderu dla programu Visual Studio 2017 Community Edition w języku angielskim może być taka sama *`C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\`* .

::: moniker-end

::: moniker range=">=vs-2019"

Folder, w którym ma zostać umieszczony plik reguły, zależy od ustawień regionalnych i używanej wersji programu Visual Studio. W wierszu polecenia programu Visual Studio 2019 lub nowszym folder reguł to *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\<locale>\`* , gdzie `<version>` wartość jest *`v160`* w programie Visual Studio 2019. `<locale>`Jest to identyfikator LCID, na przykład `1033` w języku angielskim. W programie Visual Studio 2017 folder reguł to *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . W wierszu polecenia programu Visual Studio 2015 lub starszej, folder Rules ma wartość *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* . Użyjesz innej ścieżki dla każdej wersji programu Visual Studio, która jest zainstalowana, i dla każdego języka. Na przykład domyślna ścieżka folderu dla programu Visual Studio 2019 Community Edition w języku angielskim może być taka sama *`C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v160\1033\`* .

::: moniker-end

### <a name="to-add-or-change-project-properties"></a>Aby dodać lub zmienić właściwości projektu

1. W edytorze XML Utwórz plik XML.

1. Zapisz plik w folderze reguł domyślnych. Dostosuj ścieżkę do języka i wersji programu Visual Studio. Każda reguła w oknie **strony właściwości** jest reprezentowana przez plik XML w tym folderze. Upewnij się, że plik ma unikatową nazwę w folderze.

1. Skopiuj zawartość istniejącego pliku reguł, takiego jak *`rc.xml`* , zamknij go bez zapisywania zmian, a następnie wklej zawartość w nowym pliku XML. Można skopiować dowolny plik schematu XML, który ma być używany jako szablon. Wybierz taki, który jest podobny do narzędzia.

1. W nowym pliku XML zmodyfikuj zawartość zgodnie z wymaganiami. Upewnij się, że w górnej części pliku zmieniono **nazwę reguły** i **regułę. DisplayName** .

1. Zapisz zmiany i zamknij plik.

1. Pliki XML w folderze reguł są ładowane podczas uruchamiania programu Visual Studio. Aby przetestować nowy plik, uruchom ponownie program Visual Studio.

1. W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy projekt, a następnie wybierz polecenie **Właściwości**. W oknie **strony właściwości** Sprawdź, czy istnieje nowy węzeł o nazwie reguły.

## <a name="see-also"></a>Zobacz także

[MSBuild w wierszu polecenia — C++](msbuild-visual-cpp.md)
