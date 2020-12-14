---
description: Dowiedz się więcej o:/USEPROFILE (Run PGO w trybie awaryjnym wątku)
title: /USEPROFILE (Użyj danych PGO z LTCG)
ms.date: 03/14/2018
f1_keywords:
- USEPROFILE
ms.openlocfilehash: c6c293b8467ea308dc2f7b4a4cd916cc5d9ac4c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247049"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/USEPROFILE (Uruchom PGO w trybie awaryjnym wątku)

Ta opcja konsolidatora wraz z [/LTCG (generowanie kodu w czasie konsolidacji](ltcg-link-time-code-generation.md) informuje konsolidator do skompilowania przy użyciu danych szkoleniowych dotyczących optymalizacji opartej na profilach (PGO).

## <a name="syntax"></a>Składnia

> **/USEPROFILE**[**:**{**agresywne** | **PGD =**_Nazwa pliku_}]

### <a name="arguments"></a>Argumenty

**ZACZNIE**<br/>
Ten opcjonalny argument określa, że optymalizację optymalizacji szybkości należy stosować podczas optymalizacji generowania kodu.

Plik **PGD** = *Nazwa pliku*<br/>
Określa podstawową nazwę pliku. pgd. Domyślnie konsolidator używa podstawowej nazwy pliku wykonywalnego z rozszerzeniem. pgd.

## <a name="remarks"></a>Uwagi

Opcja konsolidatora **/USEPROFILE** jest używana razem z **/LTCG** do generowania lub aktualizowania zoptymalizowanej kompilacji opartej na danych szkolenia PGO. Jest odpowiednikiem przestarzałych opcji **/LTCG: PGUPDATE** i **/LTCG: PGOPTIMIZE** .

Opcjonalny, **agresywny** argument wyłącza algorytmy heurystyczne powiązane z rozmiarami, aby próbować zoptymalizować szybkość. Może to spowodować, że optymalizacje znacząco zwiększą rozmiar pliku wykonywalnego i mogą nie zwiększyć wydajności wynikowej. Należy profilować i porównać wyniki użycia i nie używać **agresywnie**. Ten argument musi być jawnie określony; nie jest on domyślnie włączony.

Argument **PGD** określa opcjonalną nazwę pliku danych szkoleniowych, który ma być używany, tak samo jak w programie [/GENPROFILE lub/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md). Jest odpowiednikiem przestarzałego przełącznika **/PGD** . Domyślnie, lub jeśli *Nazwa pliku* nie jest określona, używany jest plik PGD o tej samej nazwie podstawowej co plik wykonywalny.

Opcja konsolidatora **/USEPROFILE** jest nowa w programie Visual Studio 2015.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >    >  stronę właściwości **optymalizacji** konsolidatora właściwości konfiguracji.

1. W właściwości **generowanie kodu w czasie konsolidacji** wybierz opcję **Użyj generowania kodu w czasie konsolidacji (/LTCG)**.

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. Wprowadź opcję **/USEPROFILE** i argumenty opcjonalne w polu **dodatkowe opcje** . Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/GENPROFILE i/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Optymalizacje profilowane](../profile-guided-optimizations.md)<br/>
[Zmienne środowiskowe dla optymalizacji Profile-Guided](../environment-variables-for-profile-guided-optimizations.md)<br/>
