---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1181'
title: Błąd narzędzi konsolidatora LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: bda05d15597d6ed82b12145d380bbe40483d7623
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341688"
---
# <a name="linker-tools-error-lnk1181"></a>Błąd narzędzi konsolidatora LNK1181

nie można otworzyć pliku wejściowego "filename"

Nie można odnaleźć konsolidatora, `filename` ponieważ nie istnieje lub nie znaleziono ścieżki.

Niektóre typowe przyczyny wystąpienia błędu LNK1181 obejmują:

- `filename` jest przywoływany jako dodatkowa zależność w linii konsolidatora, ale plik nie istnieje.

- Brak instrukcji **/LIBPATH** , która określa katalog zawierający `filename` .

Aby rozwiązać powyższe problemy, upewnij się, że wszystkie pliki, do których odwołuje się linia konsolidatora, znajdują się w systemie.  Upewnij się również, że istnieje instrukcja **/LIBPATH** dla każdego katalogu zawierającego plik zależny od konsolidatora.

Aby uzyskać więcej informacji, zobacz [Pliki lib jako dane wejściowe konsolidatora](../../build/reference/dot-lib-files-as-linker-input.md).

Kolejną możliwą przyczyną LNK1181 jest to, że długa nazwa pliku z osadzonymi spacjami nie jest ujęta w cudzysłów.  W takim przypadku konsolidator będzie rozpoznawał tylko nazwę pliku do pierwszego miejsca, a następnie przyjmuje rozszerzenie pliku. obj.  Rozwiązaniem tej sytuacji jest ujęcie w cudzysłowie długiej nazwy pliku (ścieżki i nazwy pliku).

Kompilowanie z opcją [/p (preprocess to File)](../../build/reference/p-preprocess-to-a-file.md) może spowodować, że LNK1181, ponieważ ta opcja pomija tworzenie plików. obj.

## <a name="see-also"></a>Zobacz też

[/LIBPATH (dodatkowa LIBPATH)](../../build/reference/libpath-additional-libpath.md)
