---
title: Właściwości debugera (Linux C++) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
ms.openlocfilehash: 2b55a0db001c98be72ac88c17c62b21e98ec4888
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924519"
---
# <a name="c-debugging-properties-linux-c"></a>Właściwości debugowania języka c++ (Linux C++)

::: moniker range="msvc-140"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=msvc-150"

| Właściwość | Opis | Choices |
|--|--|--|
| Zdalna maszyna debugowania | **Visual Studio 2019 w wersji 16,1** : określa maszynę, na której ma być debugowany program. Może różnić się od maszyny kompilacji zdalnej określonej na stronie [Ogólne](general-linux.md) . Możesz dodać lub edytować połączenie z maszyną docelową, korzystając z opcji **Narzędzia**  >  **Options**  >  Menedżer połączeń **między platformami**  >  **Connection Manager** . |
| Polecenie przed uruchomieniem | Polecenie uruchamiane w powłoce przed uruchomieniem debugera, które może być używane w celu wpływania na środowisko debugowania. |
| Program | Pełna ścieżka do programu, który ma być debugowany w systemie zdalnym. W przypadku pozostawienia pustej lub niezmienionej wartości domyślne bieżące dane wyjściowe projektu. |
| Argumenty programu | Argumenty wiersza polecenia do przekazania do debugowanego programu. |
| Katalog roboczy | Katalog roboczy aplikacji zdalnej. Domyślnie katalog macierzysty użytkownika. |
| Dodatkowe polecenia debugera | Dodatkowe `gdb` polecenia debugera do uruchomienia przed rozpoczęciem debugowania. |
| Numer portu debugera | Numer portu komunikacji debugera ze zdalnym debugerem. Port nie może być używany lokalnie. Ta wartość musi być dodatnia i należeć do zakresu od 1 do 65535. Jeśli nie zostanie podany, zostanie użyty bezpłatny numer portu. |
| Numer portu debugera zdalnego | Numer portu, na którym zdalny serwer debugera `gdbserver` nasłuchuje w systemie zdalnym. Port nie może być używany w systemie zdalnym. Ta wartość musi być dodatnia i należeć do zakresu od 1 do 65535. Jeśli nie zostanie podany, zostanie użyty bezpłatny numer portu zaczynający się od 4444. |
| Tryb debugowania | Określa sposób, w jaki debuger jest interfejsem `gdb` . W *trybie GDB* dyski debugera są `gdb` przenoszone przez powłokę w systemie zdalnym. W *trybie serwera gdbserver* program `gdb` działa lokalnie i łączy się z `gdbserver` uruchamianiem zdalnie. | **serwera gdbserver**<br/>**GDB** |
| Dodatkowe ścieżki wyszukiwania symboli | Dodatkowa ścieżka wyszukiwania symboli debugowania (solib-search-path). |
| Debuguj procesy podrzędne | Określa, czy włączyć debugowanie procesów podrzędnych. |
| Włącz drukowanie strukturalne języka Python | Włącz opcję całkiem drukowanie wartości wyrażeń. Obsługiwane tylko w trybie debugowania GDB. |
| Plik wizualizacji | Domyślny natywny plik wizualizacji (. Natvis) zawierający dyrektywy wizualizacji dla typów SLT. Inne pliki Natvis należące do bieżącego rozwiązania są ładowane automatycznie. |
| Mapa ścieżek plików dodatkowych źródeł | Dodatkowe równoważność ścieżki dla debugera, który ma być używany do mapowania nazw plików źródłowych systemu Windows na nazwy plików źródłowych w systemie Linux. Format to " \<windows-path> = \<linux-path> ;...". Nazwa pliku źródłowego znaleziona w ścieżce systemu Windows jest przywoływana tak, jakby została znaleziona w tej samej pozycji względnej pod ścieżką Linux. Pliki Znalezione w projekcie lokalnym nie wymagają dodatkowego mapowania. |

::: moniker-end
