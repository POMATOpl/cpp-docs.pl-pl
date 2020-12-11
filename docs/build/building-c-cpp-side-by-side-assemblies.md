---
description: 'Dowiedz się więcej o: kompilowanie zestawów równoległych C/C++'
title: Kompilowanie wykonywanych jednocześnie aplikacji C/C++
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: 174104157653eef15e67f66c67c935b7f386b71e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157064"
---
# <a name="building-cc-side-by-side-assemblies"></a>Kompilowanie wykonywanych jednocześnie aplikacji C/C++

[Zestaw równoległy](/windows/win32/SbsCs/about-side-by-side-assemblies-) to zbiór zasobów — Grupa bibliotek DLL, klas systemu Windows, serwerów com, bibliotek typów lub interfejsów — dostępna dla aplikacji do użycia w środowisku uruchomieniowym. Główną zaletą przepakowania bibliotek DLL w zestawach jest możliwość użycia wielu wersji zestawów przez aplikacje w tym samym czasie i istnieje możliwość obsługi aktualnie zainstalowanych zestawów w przypadku wydania aktualizacji.

Aplikacja C++ może korzystać z jednej lub kilku bibliotek DLL w różnych częściach aplikacji. W czasie wykonywania biblioteki DLL są ładowane do procesu głównego, a wymagany kod jest wykonywany. Aplikacja korzysta z systemu operacyjnego w celu zlokalizowania żądanych bibliotek DLL, Dowiedz się, jakie inne zależne biblioteki DLL muszą zostać załadowane, a następnie załaduj je razem z żądaną biblioteką DLL. W systemach operacyjnych Windows starszych niż Windows XP, Windows Server 2003 i Windows Vista moduł ładujący systemu operacyjnego wyszukuje zależne biblioteki DLL w folderze lokalnym aplikacji lub innym folderze określonym w ścieżce systemowej. W systemach Windows XP, Windows Server 2003 i Windows Vista moduł ładujący systemu operacyjnego może również wyszukać zależne biblioteki DLL przy użyciu pliku [manifestu](/windows/win32/sbscs/manifests) i wyszukać zestawy równoległe zawierające te biblioteki DLL.

Domyślnie, gdy biblioteka DLL jest skompilowana przy użyciu programu Visual Studio, ma [manifest aplikacji](/windows/win32/SbsCs/application-manifests) osadzony jako zasób RT_MANIFEST o identyfikatorze równym 2. Tak jak w przypadku pliku wykonywalnego, ten manifest opisuje zależności tej biblioteki DLL na innych zestawach. Przyjęto założenie, że biblioteka DLL nie jest częścią zestawu równoległego, a aplikacje, które są zależne od tej biblioteki DLL, nie będą używać manifestu aplikacji do załadowania, ale zamiast tego korzystają z modułu ładującego systemu operacyjnego w celu znalezienia tej biblioteki DLL w ścieżce systemowej.

> [!NOTE]
> Ważne jest, aby Biblioteka DLL, która używa manifestu aplikacji, do znajdowania manifestu osadzonego jako zasób o IDENTYFIKATORze równym 2. Jeśli biblioteka DLL jest wczytywana dynamicznie w czasie wykonywania (na przykład przy użyciu funkcji [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) ), moduł ładujący systemu operacyjnego ładuje zestawy zależne określone w manifeście biblioteki DLL. Manifest aplikacji zewnętrznej dla bibliotek DLL nie jest sprawdzany podczas `LoadLibrary` wywołania. Jeśli manifest nie jest osadzony, moduł ładujący może próbować załadować niepoprawne wersje zestawów lub nie można znaleźć ich w celu znalezienia zestawów zależnych.

Jeden lub kilka powiązanych bibliotek DLL można przepakować do zestawu równoległego z odpowiednim [manifestem zestawu](/windows/win32/SbsCs/assembly-manifests), który opisuje, które pliki tworzą zestaw, a także zależność zestawu na innych zestawach równoległych.

> [!NOTE]
> Jeśli zestaw zawiera jedną bibliotekę DLL, zaleca się osadzenie manifestu zestawu w tej bibliotece DLL jako zasób o IDENTYFIKATORze równym 1 i nadaj zestawowi prywatnemu taką samą nazwę jak biblioteka DLL. Na przykład jeśli nazwa biblioteki DLL jest mylibrary.dll, wartość atrybutu nazwy używana w \<assemblyIdentity> elemencie manifestu może być również biblioteką. W niektórych przypadkach, gdy biblioteka ma rozszerzenie inne niż. dll (na przykład w projekcie kontrolek ActiveX MFC tworzy bibliotekę. ocx) można utworzyć zewnętrzny manifest zestawu. W takim przypadku nazwa zestawu i jego manifest muszą być inne niż nazwa biblioteki DLL (na przykład, asembler, webassembly. manifest i weblibrary. ocx). Jednak nadal zaleca się zmianę nazwy takich bibliotek na extension.dll i osadzenie manifestu jako zasobu w celu obniżenia przyszłego kosztu konserwacji tego zestawu. Aby uzyskać więcej informacji na temat sposobu wyszukiwania zestawów prywatnych przez system operacyjny, zobacz [sekwencja wyszukiwania zestawów](/windows/win32/SbsCs/assembly-searching-sequence).

Ta zmiana może umożliwić wdrożenie odpowiednich bibliotek DLL jako [zestawu prywatnego](/windows/win32/Msi/private-assemblies) w lokalnym folderze aplikacji lub jako [zestaw współużytkowany](/windows/win32/Msi/shared-assemblies) w pamięci podręcznej zestawów winsxs. Należy wykonać kilka czynności, aby osiągnąć poprawne zachowanie środowiska uruchomieniowego nowego zestawu. są one opisane w [wytycznych dotyczących tworzenia zestawów równoległych](/windows/win32/SbsCs/guidelines-for-creating-side-by-side-assemblies). Po poprawnym utworzeniu zestawu można go wdrożyć jako zestaw współużytkowany lub prywatny razem z aplikacją, która jest od niej zależna. Jeśli instalujesz zestawy równoległe jako zestaw współużytkowany, możesz skorzystać z wytycznych opisanych w temacie [Instalowanie zestawów Win32 dla udostępniania równoczesnego w systemie Windows XP](/windows/win32/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) lub używanie [modułów scalania](/windows/win32/msi/merge-modules). Podczas instalowania zestawów równoległych jako zestawu prywatnego można po prostu skopiować odpowiednie biblioteki DLL, zasobów i manifestu zestawu w ramach procesu instalacji do folderu lokalnego aplikacji na komputerze docelowym, co zapewnia, że ten zestaw można znaleźć w czasie wykonywania (zobacz [sekwencję wyszukiwania zestawów](/windows/win32/SbsCs/assembly-searching-sequence)). Innym sposobem jest użycie [Instalator Windows](/windows/win32/Msi/windows-installer-portal) i przestrzeganie wytycznych opisanych w temacie [Instalowanie zestawów Win32 do prywatnego używania aplikacji w systemie Windows XP](/windows/win32/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp).

## <a name="see-also"></a>Zobacz też

[Kompilowanie aplikacji izolowanych C/C++](building-c-cpp-isolated-applications.md)<br/>
[Kompilowanie aplikacji izolowanych C/C++ i zestawów równoległych](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
