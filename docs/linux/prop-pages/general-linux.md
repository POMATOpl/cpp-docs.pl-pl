---
title: Właściwości ogólne (projekt systemu Linux C++)
description: Opisuje właściwości projektu systemu Linux, które można ustawić w programie Visual Studio na stronie właściwości ogólne.
ms.date: 10/14/2020
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
ms.openlocfilehash: 188e73f20eccc0e61278e154dd26e34e8613e1e9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924497"
---
# <a name="general-properties-linux-c"></a>Właściwości ogólne (Linux C++)

::: moniker range="msvc-140"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=msvc-150"

| Właściwość | Opis |
|--|--|
| Katalog wyjściowy | Określa ścieżkę względną do katalogu pliku wyjściowego. Może zawierać zmienne środowiskowe. |
| Katalog pośredni | Określa ścieżkę względną do katalogu pliku pośredniego. Może zawierać zmienne środowiskowe. |
| Nazwa obiektu docelowego | Określa nazwę pliku, który generuje ten projekt. |
| Rozszerzenie docelowe | Określa rozszerzenie pliku (na przykład `.a` ), które generuje ten projekt. |
| Rozszerzenia do usunięcia podczas czyszczenia | Rozdzielana średnikami Specyfikacja symboli wieloznacznych, dla których pliki w katalogu pośrednim mają zostać usunięte podczas czyszczenia lub odbudowy. |
| Plik dziennika kompilacji | Określa plik dziennika kompilacji, w którym ma zostać zapisany wpis, gdy rejestrowanie kompilacji jest włączone. |
| Zestaw narzędzi platformy | Określa zestaw narzędzi używany do kompilowania bieżącej konfiguracji. Jeśli nie zostanie ustawiona, używany jest domyślny zestaw narzędzi. |
| WSL *. exe pełna ścieżka | **Visual Studio 2019 w wersji 16,1** Pełna ścieżka do podsystemu Windows dla systemu Linux (WSL) używanego do kompilowania i debugowania. |
| Zdalna maszyna kompilacji | Wyświetla maszynę docelową lub urządzenie, które ma być używane do zdalnego kompilowania, wdrażania i debugowania. Możesz dodać lub edytować połączenie z maszyną docelową, korzystając z opcji **Narzędzia**  >  **Options**  >  Menedżer połączeń **między platformami**  >  **Connection Manager** .<br /> **Visual Studio 2019 w wersji 16,1** Na stronie [debugowanie](debugging-linux.md) można określić inną maszynę na potrzeby debugowania. |
| Zdalny katalog główny kompilacji | Określa ścieżkę do katalogu na komputerze zdalnym lub urządzeniu. |
| Katalog projektu kompilacji zdalnej | Określa ścieżkę do katalogu na komputerze zdalnym lub urządzeniu dla projektu. |
| Katalog zdalnego wdrażania | **Visual Studio 2019 w wersji 16,1** Określa ścieżkę katalogu na komputerze zdalnym lub urządzeniu do wdrożenia projektu. |
| Włącz kompilację przyrostową | **Visual Studio 2019 w wersji 16,7** Określa, czy Kompilacje przyrostowe mają być kompilowane przy użyciu systemu kompilacji [Ninja](https://ninja-build.org/) . Kompilacje zwykle są szybsze dla większości projektów z włączonym tym ustawieniem. |
| Zdalne kopiowanie katalogów | **Visual Studio 2019 w wersji 16,5**  Lista katalogów, które mają zostać skopiowane rekursywnie z docelowego systemu Linux. Ta właściwość ma wpływ na zdalną kopię nagłówka dla funkcji IntelliSense, ale nie kompilacji. Można go użyć, gdy **Funkcja IntelliSense używa domyślnych wartości kompilatora** , ma wartość false. Użyj **dodatkowych katalogów include** na karcie Ogólne C/C++, aby określić dodatkowe katalogi dołączane do użycia zarówno dla funkcji IntelliSense, jak i kompilacji. |
| Kopia zdalna — Wyklucz katalogi | **Visual Studio 2019 w wersji 16,5** Lista katalogów, które *nie* są kopiowane z lokalizacji docelowej systemu Linux. Zazwyczaj ta właściwość służy do usuwania podkatalogów katalogów include. |
| Technologia IntelliSense używa domyślnych wartości kompilatora | **Visual Studio 2019 w wersji 16,5** Określa, czy ma być wysyłany zapytanie do kompilatora, do którego odwołuje się ten projekt, dla jego domyślnej listy lokalizacji dołączania Te lokalizacje są automatycznie dodawane do listy katalogów zdalnych do skopiowania. Tę właściwość należy ustawić na wartość false, jeśli kompilator nie obsługuje parametrów takich jak. Zarówno kompilatory w zatoce, jak i Clang obsługują zapytania dotyczące katalogów dołączanych (na przykład `g++ -x c++ -E -v -std=c++11` ). |
| Typ konfiguracji | Określa typ danych wyjściowych generowanych przez tę konfigurację, na przykład: **Biblioteka dynamiczna (. so)** , **Biblioteka statyczna (. a)** , **aplikacja (. out)** i plik **reguł programu make** |
| Użycie STL | Określa, która standardowa biblioteka języka C++ ma być używana dla tej konfiguracji, na przykład: **udostępniona biblioteka GNU standardowa c++** lub **statyczna biblioteka GNU standardowa c++ (-static)** |

::: moniker-end
