---
description: Dowiedz się więcej o:/POGOSAFEMODE (Run PGO w trybie awaryjnym wątku)
title: /POGOSAFEMODE (Uruchom PGO w trybie awaryjnym wątku)
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: dfe8d46a3008a1d41156d077e5b87e50ac345e18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225924"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/POGOSAFEMODE (Uruchom PGO w trybie awaryjnym wątku)

**Opcja/POGOSAFEMODE jest przestarzała począwszy od programu Visual Studio 2015**. Zamiast tego użyj opcji [/GENPROFILE: Exact](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) i **/GENPROFILE: noexact** . Opcja konsolidatora **/POGOSAFEMODE** określa, że kompilacja z instrumentacją została utworzona w celu używania trybu bezpiecznego wątkowego do przechwytywania danych profilu podczas przebiegu szkoleniowego optymalizacji opartej na profilach (PGO).

## <a name="syntax"></a>Składnia

> **/POGOSAFEMODE**

## <a name="remarks"></a>Uwagi

Optymalizacja oparta na profilach (PGO) ma dwa możliwe tryby w fazie profilowania: *Tryb szybki* i *tryb bezpieczny*. Gdy profilowanie jest w trybie szybkim, używa instrukcji przyrostowej, aby zwiększyć liczniki danych. Instrukcja Increment jest szybsza, ale nie jest bezpieczna wątkowo. Gdy profilowanie działa w trybie awaryjnym, używa instrukcji z blokadą i przyrostem, aby zwiększyć liczniki danych. Ta instrukcja ma takie same funkcje jak instrukcja Increment i jest bezpieczna wątkowo, ale jest wolniejsza.

Opcja **/POGOSAFEMODE** ustawia przyrządową kompilację do używania trybu awaryjnego. Tej opcji można użyć tylko wtedy, gdy w fazie konsolidatora Instrumentacji PGO jest określony przestarzały [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) .

Domyślnie profilowanie PGO działa w trybie szybkim. **/POGOSAFEMODE** jest wymagany tylko wtedy, gdy chcesz używać trybu awaryjnego.

Aby uruchomić profilowanie PGO w trybie awaryjnym, należy użyć obu **/GENPROFILE: Exact** (preferowany) lub użyć zmiennej środowiskowej [PogoSafeMode](../environment-variables-for-profile-guided-optimizations.md) lub przełącznika konsolidatora **/POGOSAFEMODE**, w zależności od systemu. Jeśli przeprowadzasz profilowanie na komputerze z architekturą x64, musisz użyć przełącznika konsolidatora. Jeśli przeprowadzasz profilowanie na komputerze z procesorem x86, możesz użyć przełącznika konsolidatora lub zdefiniować zmienną środowiskową dla dowolnej wartości przed rozpoczęciem procesu instrumentacji PGO.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >    >  stronę właściwości **optymalizacji** konsolidatora właściwości konfiguracji.

1. W właściwości **generowanie kodu w czasie konsolidacji** wybierz opcję **profil Optymalizacja z przewodnikiem — instrument (/LTCG: PGInstrument)**.

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. Wprowadź opcję **/POGOSAFEMODE** w polu **dodatkowe opcje** . Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/GENPROFILE i/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Optymalizacje profilowane](../profile-guided-optimizations.md)<br/>
[Zmienne środowiskowe dla optymalizacji Profile-Guided](../environment-variables-for-profile-guided-optimizations.md)<br/>
