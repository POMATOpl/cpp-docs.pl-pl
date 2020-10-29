---
title: /DEPENDENTLOADFLAG (Ustaw domyślne zależne flagi ładowania)
description: Opcja/DEPENDENTLOADFLAG ustawia domyślne zależne flagi ładowania dla bibliotek DLL ładowanych przez ten moduł.
ms.date: 01/22/2020
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 8d0f53ed13143ed7ff5c507df73937a86c07b5b8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924208"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (Ustaw domyślne zależne flagi ładowania)

::: moniker range="msvc-140"

Opcja **/DEPENDENTLOADFLAG** wymaga programu Visual Studio 2017 lub nowszego.

::: moniker-end

::: moniker range=">=msvc-150"

Ustawia domyślne flagi ładowania używane, gdy system operacyjny rozwiązuje statycznie połączone Importowanie modułu.

## <a name="syntax"></a>Składnia

> **/DEPENDENTLOADFLAG** [ __:__*load_flags* ]

### <a name="arguments"></a>Argumenty

*load_flags*<br/>
Opcjonalna wartość całkowita, która określa flagi ładowania do zastosowania podczas rozpoznawania połączonych statycznie zależności importu modułu. Wartość domyślna to 0. Aby uzyskać listę obsługiwanych wartości flag, zobacz `LOAD_LIBRARY_SEARCH_*` wpisy w [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw).

## <a name="remarks"></a>Uwagi

Gdy system operacyjny rozwiązuje statycznie połączone Importowanie modułu, używa [domyślnej kolejności wyszukiwania](/windows/win32/dlls/dynamic-link-library-search-order). Użyj opcji **/DEPENDENTLOADFLAG** , aby określić wartość *load_flags* , która zmienia ścieżkę wyszukiwania używaną do rozpoznania tych importów. W obsługiwanych systemach operacyjnych zmienia kolejność wyszukiwania statycznej rozdzielczości importowania, podobnie jak w przypadku używania parametrów [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) `LOAD_LIBRARY_SEARCH` . Aby uzyskać informacje na temat kolejności wyszukiwania ustawionej przez *load_flags* , zobacz [kolejność wyszukiwania przy użyciu flag LOAD_LIBRARY_SEARCH](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

Ta flaga może służyć do wydzielenia przez jeden wektor [ataku z przesadzeniem biblioteki DLL](/windows/win32/dlls/dynamic-link-library-security) . Rozważmy na przykład aplikację, która ma statycznie połączoną bibliotekę DLL:

- Osoba atakująca może zakładać bibliotekę DLL o tej samej nazwie wcześniej w ścieżce wyszukiwania rozdzielczości importowania, takiej jak katalog aplikacji. Katalogi chronione są trudniejsze, ale nie są możliwe do zmiany przez osobę atakującą.

- Jeśli brakuje biblioteki DLL w katalogach aplikacji,%Windows%\System32 i% Windows%, rozwiązanie do importowania zostanie przechodzące do bieżącego katalogu. Osoba atakująca może zakładać bibliotekę DLL.

W obu przypadkach, jeśli określisz opcję łącza `/DEPENDENTLOADFLAG:0x800` (wartość flagi `LOAD_LIBRARY_SEARCH_SYSTEM32` ), ścieżka wyszukiwania modułu jest ograniczona do katalogu%Windows%\System32. Oferuje pewną ochronę przed atakami na inne katalogi. Aby uzyskać więcej informacji, zobacz [zabezpieczenia biblioteki dołączanej dynamicznie](/windows/win32/dlls/dynamic-link-library-security).

Aby wyświetlić wartość ustawioną przez opcję **/DEPENDENTLOADFLAG** w dowolnej bibliotece DLL, użyj polecenia [polecenia DUMPBIN](dumpbin-reference.md) z opcją [/LOADCONFIG](loadconfig.md) .

Opcja **/DEPENDENTLOADFLAG** jest nowa w programie Visual Studio 2017. Dotyczy tylko aplikacji uruchomionych w systemie Windows 10 RS1 i nowszych wersjach. Ta opcja jest ignorowana przez inne systemy operacyjne, na których jest uruchamiana aplikacja.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić opcję konsolidatora DEPENDENTLOADFLAG w środowisku deweloperskim programu Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja właściwości** > **Linker** > **wiersza polecenia** konsolidatora.

1. Wprowadź opcję w opcjach **dodatkowych** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz także

- [Dokumentacja konsolidatora MSVC](linking.md)
- [Opcje konsolidatora MSVC](linker-options.md)
- [Łączenie pliku wykonywalnego z biblioteką DLL niejawnie](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Określanie, która Metoda łączenia ma być używana](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Kolejność wyszukiwania biblioteki dołączanej dynamicznie](/windows/win32/Dlls/dynamic-link-library-search-order)
- [Zabezpieczenia biblioteki dołączanej dynamicznie](/windows/win32/dlls/dynamic-link-library-security)

::: moniker-end
