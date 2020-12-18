---
title: 'vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS'
description: vcpkg to Menedżer pakietów wiersza polecenia, który znacznie upraszcza pozyskiwanie i instalację bibliotek języka C++ typu open source w systemach Windows, macOS i Linux.
ms.custom: contperf-fy21q2
ms.date: 12/11/2020
ms.topic: overview
ms.technology: cpp-ide
ms.openlocfilehash: f937f1df718bf8dfcc0ae5166d8b9eb671d2d8ab
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2020
ms.locfileid: "97682469"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS

vcpkg to Międzyplatformowy Menedżer pakietów programu dla bibliotek C i C++. Upraszcza to pozyskiwanie i instalację bibliotek innych firm w systemach Windows, Linux i macOS. Jeśli projekt korzysta z bibliotek innych firm, zaleca się zainstalowanie ich przy użyciu programu vcpkg. vcpkg obsługuje zarówno biblioteki Open Source, jak i zastrzeżone. Wszystkie biblioteki w wykazie systemu Windows vcpkg zostały przetestowane pod kątem zgodności z programem Visual Studio 2015, Visual Studio 2017 i Visual Studio 2019. Między katalogami systemów Windows i Linux/macOS obsługuje ona tysiące bibliotek. Społeczność języka C++ jednocześnie dodaje więcej bibliotek do obu wykazów.

## <a name="how-to-get-and-use-vcpkg"></a>Jak uzyskać i używać vcpkg

Zainstaluj vcpkg, tworząc lokalny klon z repozytorium GitHub [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) . Następnie uruchom skrypt vcpkg-program inicjujący, aby go skonfigurować. Aby uzyskać szczegółowe instrukcje dotyczące instalacji, zobacz [Install vcpkg](install-vcpkg.md). Aby zintegrować vcpkg ze środowiskiem deweloperskim programu Visual Studio lub Visual Studio Code, zobacz [integrację vcpkg](integrate-vcpkg.md). Następnie, aby użyć programu vcpkg do zainstalowania lub zaktualizowania biblioteki, zobacz [Zarządzanie bibliotekami przy użyciu vcpkg](manage-libraries-with-vcpkg.md). Aby uzyskać więcej informacji o poleceniach vcpkg, zobacz [vcpkg wiersza polecenia](vcpkg-command-line-reference.md).

## <a name="how-vcpkg-works"></a>Jak działa vcpkg

Projekt vcpkg jest otwarty jako Open Source, dostępny w witrynie GitHub. *Klonowanie* lub kopia lokalna repozytorium vcpkg zawiera plik wykonywalny vcpkg i *katalog*, listę pakietów, które opisują bibliotekę i jej opcje. Każdy pakiet zawiera jeden lub więcej *portów*, informacje na temat sposobu uzyskiwania i kompilowania biblioteki ze źródeł lub pobierania wersji binarnej dla konkretnego środowiska docelowego. W przypadku korzystania z vcpkg w celu zainstalowania biblioteki program używa informacji o pakiecie i porcie do pobrania i utworzenia lokalnej kopii biblioteki w podkatalogu katalogu vcpkg, która będzie gotowa do użycia.

Gdy biblioteka jest dostępna w formularzu źródłowym, vcpkg pobiera źródła zamiast plików binarnych. Kompiluje te źródła przy użyciu najnowszej wersji kompilatora C lub C++ i narzędzi, które mogą znaleźć. W przypadku zgodności języka C++ ABI ważne jest, aby zarówno kod aplikacji, jak i wszystkie używane biblioteki były kompilowane przez tę samą wersję tego samego kompilatora. Za pomocą vcpkg, eliminujesz lub co najmniej znacznie zmniejszasz potencjalną niezgodność plików binarnych i problemy, które mogą być przyczyną. W zespołach, które standaryzacją określoną wersję kompilatora, jeden członek zespołu może używać vcpkg do pobierania źródeł i kompilowania zestawu plików binarnych. Wszyscy członkowie zespołu mogą pobierać i kompilować wspólne biblioteki. Jeden członek zespołu może użyć **`vcpkg export`** polecenia, aby utworzyć wspólny plik zip plików binarnych i nagłówków lub pakiet NuGet. Następnie można łatwo udostępnić go innym członkom zespołu.

## <a name="customize-vcpkg-instances-for-different-targets"></a>Dostosuj wystąpienia vcpkg dla różnych elementów docelowych

Można klonować wiele kopii lub *wystąpień* vcpkg na maszynie oraz dostosowywać każdy z nich do określonych celów. W każdym wystąpieniu można zainstalować różne biblioteki, a nawet różne wersje bibliotek niż te, które znajdują się w wykazie publicznym. Każde wystąpienie może być ustawione do tworzenia niestandardowej kolekcji bibliotek przy użyciu preferowanych opcji kompilatora. Każde wystąpienie jest środowiskiem autonomicznym z własną kopią vcpkg.exe, która działa tylko w jego własnej hierarchii. vcpkg nie jest dodawany do żadnych zmiennych środowiskowych i nie ma zależności w rejestrze systemu Windows ani w programie Visual Studio.

Można również utworzyć klon vcpkg z bibliotekami prywatnymi w kolekcji ports. Można dodać port, który pobiera wstępnie skompilowane pliki binarne i nagłówki. Następnie napisz plik *Portfile. CMAKE* , który po prostu kopiuje te pliki do preferowanej lokalizacji.

## <a name="the-vcpkg-folder-hierarchy"></a>Hierarchia folderów vcpkg

Wszystkie funkcje i dane vcpkg są samodzielne w jednej hierarchii katalogów na wystąpienie. Brak ustawień rejestru lub zmiennych środowiskowych. Na komputerze może być dowolna liczba wystąpień vcpkg i nie będą one zakłócać działania siebie.

Zawartość wystąpienia vcpkg:

- *`buildtrees`* -Zawiera podfoldery źródeł, z których jest skompilowana każda biblioteka.
- *`docs`* — Dokumentacja i przykłady.
- *`downloads`* — Zbuforowane kopie pobranych narzędzi lub źródeł. vcpkg Przeszukuj tutaj najpierw po uruchomieniu polecenia install.
- *`installed`* -Zawiera nagłówki i pliki binarne dla każdej zainstalowanej biblioteki. Gdy integrujesz się z programem Visual Studio, oznacza to, że zostanie on dodany do ścieżki wyszukiwania.
- *`packages`* — Wewnętrzny folder do przemieszczania między instalacjami.
- *`ports`* — Pliki opisujące każdą bibliotekę w wykazie, jej wersję i lokalizację, w której należy ją pobrać. W razie konieczności możesz dodać własne porty.
- *`scripts`* — Skrypty (CMake, PowerShell) używane przez vcpkg.
- *`toolsrc`* -C++ kod źródłowy dla vcpkg i powiązanych składników.
- *`triplets`* -Zawiera ustawienia dla każdej obsługiwanej platformy docelowej (na przykład x86-Windows lub x64-platformy UWP).

## <a name="telemetry"></a>Telemetria

vcpkg zbiera dane dotyczące użycia, aby pomóc nam w ulepszaniu środowiska. Dane zbierane przez firmę Microsoft są anonimowe. Możesz zrezygnować z telemetrii przez ponowne uruchomienie **`bootstrap-vcpkg.bat`** **`bootstrap-vcpkg.sh`** skryptu lub przy użyciu **`-disableMetrics`** opcji. Lub Przekaż **`--disable-metrics`** opcję do vcpkg w wierszu polecenia. Możesz również wyłączyć metryki przez ustawienie `VCPKG_DISABLE_METRICS` zmiennej środowiskowej.

## <a name="send-feedback-about-vcpkg"></a>Wyślij opinię na temat vcpkg

Użyj **`vcpkg contact --survey`** polecenia, aby wysłać opinię do firmy Microsoft dotyczącej vcpkg, w tym raportów o błędach i sugestii dotyczących funkcji. Aby uzyskać więcej informacji, zobacz [vcpkg — dokumentacja wiersza polecenia](vcpkg-command-line-reference.md).

## <a name="see-also"></a>Zobacz także

[vcpkg w serwisie GitHub](https://github.com/Microsoft/vcpkg)\
[Zainstaluj vcpkg](install-vcpkg.md)\
[Integruj vcpkg](integrate-vcpkg.md)\
[Zarządzanie bibliotekami za pomocą vcpkg](manage-libraries-with-vcpkg.md)\
[vcpkg — dokumentacja wiersza polecenia](vcpkg-command-line-reference.md)\
[Szybki Start](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Często zadawane pytania](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
