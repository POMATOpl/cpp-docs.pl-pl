---
title: 'Strona właściwości Niestandardowy krok budowania: ogólne'
description: W tym artykule opisano właściwości dostępne na stronie niestandardowy krok kompilacji w oknie dialogowym strony właściwości.
ms.date: 10/27/2020
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
ms.openlocfilehash: 53f2deef931821981b3301f44ba37660975fb811
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907587"
---
# <a name="custom-build-step-property-page-general"></a>Strona właściwości Niestandardowy krok budowania: ogólne

Dla każdej konfiguracji projektu i docelowej kombinacji platformy w projekcie można określić niestandardowy krok do wykonania podczas kompilowania projektu.

Aby uzyskać wersję systemu Linux na tej stronie, zobacz [właściwości niestandardowego kroku kompilacji (Linux C++)](../../linux/prop-pages/custom-build-step-linux.md).

## <a name="general-page"></a>Strona ogólna

- **Wiersz polecenia**

   Polecenie wykonywane przez krok niestandardowej kompilacji.

- **Opis**

   Komunikat, który jest wyświetlany podczas wykonywania kroku niestandardowej kompilacji.

- **Dane wyjściowe**

   Plik wyjściowy, generowany przez krok niestandardowej kompilacji. To ustawienie jest wymagane, aby kompilacje przyrostowe działały poprawnie.

- **Dodatkowe zależności**

   Rozdzielana średnikami lista wszelkich dodatkowych plików wejściowych dla kroku niestandardowej kompilacji.

- **Wykonaj po i wykonaj przed**

   Te opcje definiują, kiedy krok niestandardowej kompilacji jest uruchamiany w procesie kompilacji w stosunku do wymienionych celów. Najczęściej wymienione cele to `BuildGenerateSources` , `BuildCompile` , i `BuildLink` , ponieważ reprezentują główne kroki procesu kompilacji. Inne często wymienione cele to `Midl` , `CLCompile` , i `Link` .

- **Traktuj dane wyjściowe jako zawartość**

   Ta opcja ma znaczenie tylko w przypadku aplikacji platforma uniwersalna systemu Windows lub Windows Phone, które obejmują wszystkie pliki zawartości w *`.appx`* pakiecie.

### <a name="to-specify-a-custom-build-step"></a>Aby określić krok niestandardowej kompilacji

1. Na pasku menu wybierz **Project**  >  **Właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. W oknie dialogowym **strony właściwości** przejdź do strony Ogólne w obszarze **Właściwości konfiguracji**  >  **niestandardowe krok kompilacji**  >  **General** .

1. Zmodyfikuj ustawienia.

## <a name="see-also"></a>Zobacz także

[Odwołanie do strony właściwości projektu C++](property-pages-visual-cpp.md)
