---
description: 'Dowiedz się więcej o programie: Określanie zdarzeń kompilacji'
title: Określanie zdarzeń kompilacji
ms.date: 12/28/2017
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
ms.openlocfilehash: 1d1dc9a1f0e379c3abe36117beaf9ef58bcbd064
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275402"
---
# <a name="specifying-build-events"></a>Określanie zdarzeń kompilacji

Możesz użyć zdarzeń kompilacji, aby określić polecenia, które są uruchamiane przed rozpoczęciem kompilacji, przed procesem linku lub po zakończeniu kompilacji.

Zdarzenia kompilacji są wykonywane tylko wtedy, gdy kompilacja pomyślnie osiągnie te punkty w procesie kompilacji. Jeśli wystąpi błąd w kompilacji, zdarzenie wykonywane *po kompilacji* nie wystąpi. Jeśli błąd występuje przed fazą konsolidacji, nie wystąpi ani *link poprzedzający* , ani zdarzenie *po kompilacji* . Ponadto jeśli żadne pliki nie muszą być połączone, zdarzenie *poprzedzające połączenie* nie zostanie wykonane. Zdarzenie *poprzedzające połączenie* jest również niedostępne w projektach, które nie zawierają kroku linku.

Jeśli żadne pliki nie muszą być skompilowane, nie wystąpią żadne zdarzenia kompilacji.

Aby uzyskać ogólne informacje na temat zdarzeń kompilacji, zobacz [Opis niestandardowych kroków kompilacji i zdarzeń kompilacji](understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-build-event"></a>Aby określić zdarzenie kompilacji

1. W **Eksplorator rozwiązań** wybierz projekt, dla którego chcesz określić zdarzenie kompilacji.

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](working-with-project-properties.md).

1. W folderze **zdarzenia kompilacji** wybierz stronę właściwości zdarzenia kompilacji.

1. Określ właściwości skojarzone ze zdarzeniem kompilacji:

   - W **wierszu polecenia** określ polecenie tak, jakby było ono określane w wierszu polecenia. Określ prawidłowe polecenie lub plik wsadowy oraz wszystkie wymagane pliki wejściowe lub wyjściowe. Określ polecenie **call** Batch przed nazwą pliku wsadowego, aby zagwarantować, że wszystkie kolejne polecenia są wykonywane.

      Wiele plików wejściowych i wyjściowych można określić symbolicznie przy użyciu makr MSBuild. Aby uzyskać informacje na temat sposobu określania lokalizacji plików lub nazw zestawów plików, zobacz [Common MACROS for Build Commands and Properties](reference/common-macros-for-build-commands-and-properties.md).

      Ponieważ znak "%" jest zastrzeżony przez MSBuild, w przypadku określenia zmiennej środowiskowej Zamień każdy **%** znak ucieczki na **%25** szesnastkową sekwencję ucieczki. Na przykład Zamień **% windir%** na **% 25WINDIR %25**. MSBuild zastępuje każdą sekwencję **%25** **%** znakiem przed uzyskaniem dostępu do zmiennej środowiskowej.

   - W polu **Opis** wpisz opis tego zdarzenia. W przypadku wystąpienia tego zdarzenia opis jest drukowany w oknie **danych wyjściowych** .

   - W obszarze **wykluczone z kompilacji** Określ **wartość tak** , jeśli nie chcesz uruchamiać zdarzenia.

## <a name="see-also"></a>Zobacz też

[Ogólne informacje o niestandardowych krokach budowania lub zdarzeniach kompilacji](understanding-custom-build-steps-and-build-events.md)<br>
[Typowe makra dla właściwości i poleceń kompilacji](reference/common-macros-for-build-commands-and-properties.md)<br>
[Rozwiązywanie problemów z dostosowaniami kompilacji](troubleshooting-build-customizations.md)
