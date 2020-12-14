---
description: Dowiedz się więcej o:/PGD (Określ bazę danych dla optymalizacji Profile-Guided)
title: /PGD (Określ bazę danych dla optymalizacji sterowanych profilem)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: 7030ddaef33c6ee794c470df2c42c72d78555369
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225989"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Określ bazę danych dla optymalizacji sterowanych profilem)

**Opcja/PGD jest przestarzała.** Począwszy od programu Visual Studio 2015, Preferuj zamiast tego Opcje konsolidatora [/GENPROFILE lub/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) . Ta opcja służy do określania nazwy pliku. PGD używanego przez proces optymalizacji z przewodnikiem.

## <a name="syntax"></a>Składnia

> **/PGD:**_filename_

## <a name="argument"></a>Argument

*Nazwa pliku*<br/>
Określa nazwę pliku. pgd, który jest używany do przechowywania informacji o uruchomionym programie.

## <a name="remarks"></a>Uwagi

W przypadku używania przestarzałej opcji [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) należy użyć **/PGD** do określenia niedomyślnej nazwy lub lokalizacji pliku. pgd. Jeśli nie określisz **/PGD**, nazwa podstawowa pliku. PGD jest taka sama jak nazwa podstawowa pliku (. exe lub. dll) i jest tworzona w tym samym katalogu, z którego wywołano połączenie.

W przypadku używania przestarzałej opcji **/LTCG: PGOPTIMIZE** Użyj opcji **/PGD** , aby określić nazwę pliku. PGD do użycia w celu utworzenia zoptymalizowanego obrazu. Argument *filename* powinien być zgodny z *nazwą pliku* określoną do **/LTCG: PGINSTRUMENT**.

Aby uzyskać więcej informacji, zapoznaj się z tematem [optymalizacje](../profile-guided-optimizations.md)profilowane.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >    >  stronę właściwości **optymalizacji** konsolidatora właściwości konfiguracji.

1. Zmodyfikuj właściwość **baza danych z przewodnikiem** . Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)<br/>
