---
title: pgosweep
description: Użyj polecenia pgosweep, aby zapisać dane profilu do pliku PGC do użycia w optymalizacji profilowanej.
ms.date: 10/23/2020
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.openlocfilehash: be96d0f092ff65867c304ddf5eb41c0754f6e4be
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497181"
---
# <a name="pgosweep"></a>pgosweep

Używane w optymalizacji profilowanej do zapisywania wszystkich danych profilu z działającego programu do pliku PGC.

## <a name="syntax"></a>Składnia

> **`pgosweep`**[*Opcje*] *image* *pgcfile* obrazów

### <a name="parameters"></a>Parametry

*Opcje*\
Obowiązkowe Prawidłowe wartości dla *opcji* są następujące:

- **`/?`** lub **`/help`** wyświetla komunikat pomocy.

- **`/reset`** resetuje liczbę do zera po wyczyszczeniu. Jest to zachowanie domyślne.

- **`/pid:n`** Wyczyść tylko określony identyfikator PID, gdzie *n* jest numerem PID.

- **`/wait`** czeka na zakończenie określonego identyfikatora PID przed zebraniem liczników.

- **`/onlyzero`** nie zapisuje pliku PGC, tylko zerowe zliczenia.

- **`/pause`** wstrzymuje zbieranie danych w systemie.

- **`/resume`** wznawia zbieranie danych w systemie.

- **`/noreset`** zachowuje liczbę w strukturach danych środowiska uruchomieniowego.

*Image*\
Pełna ścieżka pliku EXE lub DLL, który został utworzony przy użyciu [`/GENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) [`/FASTGENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) opcji, lub [`/LTCG:PGINSTRUMENT`](reference/ltcg-link-time-code-generation.md) .

*pgcfile*\
Plik PGC, w którym to polecenie zapisuje liczby danych.

## <a name="remarks"></a>Uwagi

**`pgosweep`** Polecenie działa w programach, które zostały skompilowane przy użyciu opcji [ `/GENPROFILE` lub `/FASTGENPROFILE` ](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) lub opcji przestarzałe [`/LTCG:PGINSTRUMENT`](reference/ltcg-link-time-code-generation.md) . Przerywa uruchomiony program i zapisuje dane profilu do nowego pliku PGC. Domyślnie polecenie Resetuje licznik po każdej operacji zapisu. W przypadku określenia **`/noreset`** opcji polecenie spowoduje zapisanie wartości, ale nie zresetowanie ich w uruchomionym programie. Ta opcja umożliwia duplikowanie danych w przypadku późniejszego pobrania danych profilu.

Alternatywnym zastosowaniem programu **`pgosweep`** jest pobranie informacji o profilu tylko dla normalnego działania aplikacji. Na przykład można uruchomić polecenie **`pgosweep`** wkrótce po uruchomieniu aplikacji i odrzucić ten plik. To polecenie spowoduje usunięcie danych profilu skojarzonych z kosztami uruchomienia. Następnie można uruchomić program **`pgosweep`** przed zakończeniem aplikacji. Teraz zebrane dane zawierają informacje o profilu tylko od momentu, w którym użytkownik może korzystać z programu.

Po nazwie pliku PGC (przy użyciu parametru *pgcfile* ) można użyć formatu standardowego, czyli *`appname!n.pgc`* . *N* reprezentuje zwiększenie wartości liczbowej dla każdego pliku. Jeśli używasz tego formatu, kompilator automatycznie odnajdzie te dane w **`/LTCG /USEPROFILE`** **`/LTCG:PGO`** fazie lub. Jeśli nie używasz formatu standardowego, należy użyć [`pgomgr`](pgomgr.md) do scalania plików PGC.

> [!NOTE]
> To narzędzie można uruchomić tylko z poziomu wiersza polecenia programu Visual Studio Developer. Nie można uruchomić go z poziomu wiersza polecenia systemu lub Eksploratora plików.

Informacje o sposobach przechwytywania danych profilu z pliku wykonywalnego znajdują się w temacie [`PgoAutoSweep`](pgoautosweep.md) .

## <a name="example"></a>Przykład

W tym przykładzie polecenie **`pgosweep`** zapisuje informacje o bieżącym profilu dla programu *`myapp.exe`* *`myapp!1.pgc`* .

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Zobacz też

[Optymalizacje profilowane](profile-guided-optimizations.md)\
[PgoAutoSweep](pgoautosweep.md)
