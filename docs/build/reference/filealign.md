---
description: Dowiedz się więcej na temat:/FILEALIGN (Wyrównaj sekcje w plikach)
title: /FILEALIGN (Wyrównaj sekcje w plikach)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: a67cf682c8fe55b80b2253864e08919e08242f74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192165"
---
# <a name="filealign-align-sections-in-files"></a>/FILEALIGN (Wyrównaj sekcje w plikach)

Opcja konsolidatora **/FILEALIGN** umożliwia określenie wyrównania sekcji zapisaną w pliku wyjściowym jako wielokrotność określonego rozmiaru.

## <a name="syntax"></a>Składnia

> __/FILEALIGN:__*rozmiar*

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Rozmiar wyrównania sekcji w bajtach, który musi być potęgą liczby dwa.

## <a name="remarks"></a>Uwagi

Opcja **/FILEALIGN** powoduje, że konsolidator wyrównuje każdą sekcję w pliku wyjściowym na granicy, która jest wielokrotnością wartości *rozmiaru* . Domyślnie konsolidator nie używa stałego rozmiaru wyrównania.

Opcji **/FILEALIGN** można użyć, aby zwiększyć wydajność dysku lub zwiększyć szybkość ładowania strony z dysku. Mniejszy rozmiar sekcji może być przydatny w przypadku aplikacji uruchamianych na mniejszych urządzeniach lub do przechowywania mniejszych plików do pobrania. Wyrównanie sekcji na dysku nie ma wpływu na wyrównanie w pamięci.

Użyj [polecenia DUMPBIN](dumpbin-reference.md) , aby wyświetlić informacje o sekcjach w pliku wyjściowym.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **wiersza polecenia** w folderze **konsolidatora** .

1. Wpisz nazwę opcji **/FILEALIGN:** i rozmiar w polu **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
