---
title: Tworzenie projektu systemu Linux MSBuild C++ w programie Visual Studio
ms.date: 10/15/2020
description: Utwórz nowy projekt systemu Linux oparty na programie MSBuild w programie Visual Studio.
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 458a26408bfd29b714150e5259fd23807c9b2908
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921636"
---
# <a name="create-a-linux-msbuild-c-project-in-visual-studio"></a>Tworzenie projektu systemu Linux MSBuild C++ w programie Visual Studio

::: moniker range="msvc-140"

Projekty systemu Linux są dostępne w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range="msvc-150"

Najpierw upewnij się, że masz zainstalowane **obciążenie deweloperskie systemu Linux** dla programu Visual Studio. Aby uzyskać więcej informacji, zobacz [pobieranie, Instalowanie i Konfigurowanie obciążenia systemu Linux](download-install-and-setup-the-linux-development-workload.md).

W przypadku kompilacji na wielu platformach zalecamy użycie CMake. Obsługa CMake jest bardziej kompletna w programie Visual Studio 2019. Jeśli CMake nie jest opcją i masz istniejące rozwiązanie Windows Visual Studio, które ma zostać rozbudowane do kompilacji dla systemu Linux, możesz dodać projekt programu Visual Studio Linux do rozwiązania systemu Windows wraz z projektem **elementów współużytkowanych** . Umieść kod, który jest współużytkowany między obiema platformami w projekcie elementy udostępnione, i Dodaj odwołanie do tego projektu z projektów systemu Windows i Linux.

## <a name="to-create-a-new-linux-project"></a>Aby utworzyć nowy projekt systemu Linux

Aby utworzyć nowy projekt systemu Linux w programie Visual Studio 2017, wykonaj następujące kroki:

1. Wybierz pozycję **plik > nowy projekt** w programie Visual Studio lub naciśnij **klawisze Ctrl + Shift + N** .
1. Wybierz węzeł **Visual C++ > wielu Platform > Linux** , a następnie wybierz typ projektu do utworzenia. Wprowadź **nazwę** i **lokalizację** , a następnie wybierz **przycisk OK** .

   ![Zrzut ekranu przedstawiający okno dialogowe Nowy projekt z wybraną pozycją Visual C plus plus > cross platform > Linux, wszystkie typy projektów o nazwie i pola tekstowe Nazwa i lokalizacja są również wywoływane.](media/newproject.png)

   | Typ projektu | Opis |
   | ------------ | --- |
   | **Miganie (Raspberry)** | Projekt przeznaczony dla urządzenia Raspberry Pi z przykładowym kodem, który miga diody LED |
   | **Aplikacja konsolowa (Linux)** | Projekt przeznaczony dla dowolnego komputera z systemem Linux z przykładowym kodem, który wyprowadza tekst do konsoli |
   | **Pusty projekt (Linux)** | Projekt przeznaczony dla dowolnego komputera z systemem Linux bez przykładowego kodu |
   | **Projekt pliku reguł programu make (Linux)** | Projekt przeznaczony dla dowolnego komputera z systemem Linux utworzony przy użyciu standardowego systemu kompilacji pliku reguł programu make |

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie projektu programu MSBuild dla systemu Linux](configure-a-linux-project.md)

::: moniker-end

::: moniker range="msvc-160"

Najpierw upewnij się, że masz zainstalowane **obciążenie deweloperskie systemu Linux** dla programu Visual Studio. Aby uzyskać więcej informacji, zobacz [pobieranie, Instalowanie i Konfigurowanie obciążenia systemu Linux](download-install-and-setup-the-linux-development-workload.md).

Podczas tworzenia nowego projektu C++ dla systemu Linux w programie Visual Studio można utworzyć projekt programu Visual Studio lub projekt CMake. W tym artykule opisano sposób tworzenia projektu programu Visual Studio. Ogólnie rzecz biorąc, w przypadku nowych projektów, które mogą obejmować kod w języku Open Source, lub planujesz kompilację dla wieloplatformowego opracowywania, zalecamy użycie CMake z programem Visual Studio. Projekt CMake umożliwia tworzenie i debugowanie tego samego projektu zarówno w systemie Windows, jak i Linux. Aby uzyskać więcej informacji, zobacz [Tworzenie i Konfigurowanie projektu systemu Linux CMAKE](cmake-linux-project.md).

Jeśli masz istniejące rozwiązanie Windows Visual Studio, które chcesz rozłożyć na kompilację dla systemu Linux, a CMake nie jest opcją, możesz dodać projekt programu Visual Studio Linux do rozwiązania systemu Windows wraz z projektem **elementów współużytkowanych** . Umieść kod, który jest współużytkowany między obiema platformami w projekcie elementy udostępnione, i Dodaj odwołanie do tego projektu z projektów systemu Windows i Linux.

## <a name="create-a-new-linux-project"></a>Tworzenie nowego projektu systemu Linux

Aby utworzyć nowy projekt systemu Linux w programie Visual Studio 2019, wykonaj następujące kroki:

1. Wybierz pozycję **plik > nowy projekt** w programie Visual Studio lub naciśnij **klawisze Ctrl + Shift + N** . Zostanie wyświetlone okno dialogowe Tworzenie nowego projektu.
1. W polu tekstowym **Wyszukiwanie szablonów** Wprowadź system **Linux** , aby wyświetlić listę dostępnych szablonów dla projektów systemu Linux.
1. Wybierz typ projektu do utworzenia, na przykład **Aplikacja konsolowa** , a następnie wybierz przycisk **dalej** . Wprowadź **nazwę** i **lokalizację** , a następnie wybierz pozycję **Utwórz** .

   ![Zrzut ekranu okna dialogowego Nowy projekt z listą rozwijaną język ustawioną na C++ i listę rozwijaną platforma ustawionymi na system Linux.](media/newproject-vs2019.png)

   | Typ projektu | Opis |
   | ------------ | --- |
   | **Projekt Raspberry Pi** | Projekt przeznaczony dla urządzenia Raspberry Pi z przykładowym kodem, który miga diody LED |
   | **Aplikacja konsoli** | Projekt przeznaczony dla dowolnego komputera z systemem Linux z przykładowym kodem, który wyprowadza tekst do konsoli |
   | **Pusty projekt** | Projekt przeznaczony dla dowolnego komputera z systemem Linux bez przykładowego kodu |
   | **Projekt pliku reguł programu make** | Projekt przeznaczony dla dowolnego komputera z systemem Linux utworzony przy użyciu standardowego systemu kompilacji pliku reguł programu make |
   | **Projekt CMake** | Projekt przeznaczony dla dowolnego komputera z systemem Linux utworzony przy użyciu systemu kompilacji CMake |

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie projektu narzędzia MSBuild w systemie Linux](configure-a-linux-project.md)

::: moniker-end
