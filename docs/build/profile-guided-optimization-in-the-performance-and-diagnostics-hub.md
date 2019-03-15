---
title: Optymalizacja sterowana profilem w Centrum Wydajności i Diagnostyki
ms.date: 11/19/2018
ms.assetid: dc3a1914-dbb6-4401-bc63-10665a8c8943
ms.openlocfilehash: e1aaf64c18ebde29e6ea0d6b4b6bdad66f21a435
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823289"
---
# <a name="profile-guided-optimization-in-the-visual-studio-2013-performance-and-diagnostics-hub"></a>Optymalizacja sterowana profilem w Visual Studio 2013 Centrum wydajności i diagnostyki

Jeśli używasz programu Visual Studio 2013, optymalizacja sterowana profilem Visual c++ dla dodatku typu plug-in w Centrum wydajności i diagnostyki usprawnia proces optymalizacji profilowe z przewodnikiem dla deweloperów. Możesz [Pobierz wtyczkę](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) z witryny sieci Web programu Visual Studio. Wtyczka nie jest obsługiwana w nowszych wersjach programu Visual Studio.

Profilowe z przewodnikiem Optymalizacja (PGO) pomaga tworzyć kompilacje x86 i x64 aplikacje natywne, które są zoptymalizowane pod kątem przez użytkowników wchodzić w interakcje z nimi. PGO to proces obejmujący wiele kroków: Tworzenie kompilacji aplikacji, który został zinstrumentowany na potrzeby profilowania, a następnie wykonaj "szkoleniowe." Oznacza to, że uruchamiasz instrumentowanej aplikacji przy użyciu typowych scenariuszy interakcji użytkownika. Zapisanie przechwycone dane profilowania i ponownie skompiluj aplikację za pomocą wyników przeprowadzenie optymalizacji całego programu. Mimo że te kroki można wykonać osobno w programie Visual Studio lub w wierszu polecenia, wtyczka PGO centralizuje i upraszcza ten proces. Wtyczka PGO Ustawia wszystkie wymagane opcje, przeprowadzi Cię przez kolejne kroki, dowiesz się, analizę i następnie używa wyników do konfigurowania kompilacji, aby zoptymalizować każdej funkcji dla rozmiar lub prędkość. Wtyczka PGO również ułatwia ponowne uruchomienie aplikacji szkolenia i zaktualizować dane optymalizacji kompilacji, ponieważ zmian w kodzie.

## <a name="prerequisites"></a>Wymagania wstępne

Należy najpierw [Pobierz wtyczkę PGO](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) i zainstaluj go w programie Visual Studio, zanim użyjesz go w Centrum wydajności i diagnostyki.

## <a name="walkthrough-using-the-pgo-plug-in-to-optimize-an-app"></a>Przewodnik: Optymalizowanie aplikacji za pomocą wtyczki PGO

Najpierw utworzymy podstawową aplikację pulpitu Win32 w programie Visual Studio. Jeśli masz już aplikację natywną, którą chcesz zoptymalizować, możesz go użyć i pominąć ten krok.

### <a name="to-create-an-app"></a>Aby utworzyć aplikację

1. Na pasku menu wybierz **pliku**, **New**, **projektu**.

1. W okienku po lewej stronie **nowy projekt** okna dialogowego rozwiń **zainstalowane**, **szablony**, **Visual C++**, a następnie wybierz pozycję  **MFC**.

1. W środkowym okienku wybierz **aplikacji MFC**.

1. Określ nazwę dla projektu — na przykład **SamplePGOProject**— w **nazwa** pole. Wybierz **OK** przycisku.

1. Na **Przegląd** strony **Kreator aplikacji MFC** okna dialogowego wybierz **Zakończ** przycisku.

Następnie ustaw dla konfiguracji kompilacji aplikacji do wersji na "gotowy" on PGO kompilacji i kroki szkolenia.

### <a name="to-set-the-build-configuration"></a>Aby ustawić konfigurację kompilacji

1. Na pasku menu wybierz **kompilacji**, **programu Configuration Manager**.

1. W **programu Configuration Manager** okna dialogowego wybierz **aktywną konfigurację rozwiązania** przycisk listy rozwijanej i wybierz pozycję **wersji**. Wybierz **Zamknij** przycisku.

Otwórz Centrum wydajności i diagnostyki, na pasku menu wybierz **analizy**, **wydajności i diagnostyki**. Spowoduje to otwarcie strony sesji diagnostyki, która dysponuje narzędziami analizy, które są dostępne dla danego typu projektu.

![PGO w Centrum wydajności i diagnostyki](media/pgofig0hub.png "PGO w Centrum wydajności i diagnostyki")

W **dostępnych narzędzi**, wybierz opcję **profilowana Optymalizacja** pole wyboru. Wybierz **Start** przycisk, aby uruchomić dodatek typu plug-in PGO.

![Strona wprowadzenia PGO](media/pgofig1start.png "strona wprowadzenia PGO")

**Profilowana Optymalizacja** strony opisano kroki, używa wtyczki, aby zwiększyć wydajność aplikacji. Wybierz **Start** przycisku.

![Strona Instrumentacji PGO](media/pgofig2instrument.png "PGO Instrumentacji strony")

W **Instrumentacji** sekcji, możesz użyć **szkolenia początkowo jest włączona** opcję, aby wybrać, czy mają zostać dołączone do fazy uruchamiania aplikacji w ramach szkolenia. Jeśli ta opcja nie jest zaznaczone, dane szkoleniowe nie została zarejestrowana w uruchomionej aplikacji instrumentowanych, aż jawnie włączyć szkolenia.

Wybierz **Instrument** przycisk, aby utworzyć aplikację przy użyciu specjalnego zestawu opcji kompilatora. Kompilator wstawia sondy instrukcje w wygenerowanym kodzie. Te instrukcje rejestrowania danych profilowania w fazie szkolenia.

![Strona kompilację instrumentowaną PGO](media/pgofig3build.PNG "PGO kompilację instrumentowaną strony")

Aplikacja jest uruchomiane automatycznie po zakończeniu kompilacji instrumentowanej aplikacji.

Jeśli występują błędy lub ostrzeżenia podczas kompilowania, popraw je, a następnie wybierz **ponowne uruchomienie kompilacji** ponownie uruchomić kompilację instrumentowaną.

Gdy aplikacja jest uruchomiona, można użyć **Rozpocznij szkolenie** i **szkolenia Wstrzymaj** linki w **szkolenia** sekcji, aby kontrolować podczas profilowania informacje są rejestrowane. Możesz użyć **Zatrzymaj aplikację** i **Uruchom aplikację** łącza, aby zatrzymać i ponownie uruchom aplikację.

![Strony szkolenia PGO](media/pgofig4training.PNG "strony szkolenia PGO")

Podczas szkolenia, przechodzą przez scenariuszy użytkownika do przechwytywania informacji profilowania, wymagającym PGO wtyczka do optymalizacji kodu. Po zakończeniu szkolenia, zamknij aplikację, lub wybierz **Zatrzymaj aplikację** łącza. Wybierz **analizy** przycisk, aby rozpocząć krok analizy.

Po zakończeniu analizy **analizy** sekcji przedstawiono raport z informacjami profilowania, przechwyconą w fazie szkolenia scenariusza użytkownika. Ten raport służy do sprawdzenia, które funkcje aplikacji o nazwie większość i wydano najwięcej czasu w. Wtyczka PGO informacje są używane do określenia aplikacji, która działa pod kątem szybkości i którego ma zostać Optymalizuj pod kątem rozmiaru. Wtyczka PGO konfiguruje optymalizacje kompilacji do utworzenia aplikacji najmniejsza, fastest dla scenariuszy użytkowników, które rejestrowane podczas szkolenia.

![Strona analizy PGO](media/pgofig5analyze.png "strona analizy PGO")

Jeśli szkolenia przechwytywane oczekiwane informacje profilowania, możesz wybrać **Zapisz zmiany** można zapisać danych profilu przeanalizowany w projekcie, aby zoptymalizować kompilacji w przyszłości. Aby odrzucić dane profilu i szkolenie za pośrednictwem są uruchamiane od początku, wybierz opcję **ponownie przeprowadzić szkolenia**.

Plik danych profilu jest zapisywany w projekcie w **dane szkoleniowe PGO** folderu. Te dane są używane do kontrolowania ustawień optymalizacji kompilatora kompilacji w swojej aplikacji.

![Plik danych PGO w Eksploratorze rozwiązań](media/pgofig6data.png "PGO pliku danych w Eksploratorze rozwiązań")

Po analizie usługa PGO wtyczka Ustawia opcje kompilacji w projekt, aby użyć danych profilowych selektywnie zoptymalizować aplikację, podczas kompilacji. Można modyfikować i tworzenie aplikacji przy użyciu tych samych danych profilu. Podczas kompilowania aplikacji, dane wyjściowe kompilacji raporty, jak wiele funkcji i instrukcje, które zostały zoptymalizowane przy użyciu danych profilu.

![PGO dane wyjściowe diagnostyki](media/pgofig7diagnostics.png "PGO dane wyjściowe diagnostyki")

Po wprowadzeniu zmian w kodzie istotne podczas projektowania może być konieczne ponowne szkolenie aplikację, aby uzyskać najlepszą optymalizację. Firma Microsoft zaleca ponowne szkolenie aplikację, kiedy dane wyjściowe kompilacji, mniej niż 80 procent, funkcji lub instrukcje zostały zoptymalizowane przy użyciu danych profilu.