---
description: Dowiedz się więcej o:/HEAP (Ustaw rozmiar sterty)
title: /HEAP (Ustaw rozmiar stosu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- VC.Project.VCLinkerTool.HeapReserveSize
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
ms.openlocfilehash: 9831180925d5d669c799982d021d75ea31a2dae5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191670"
---
# <a name="heap-set-heap-size"></a>/HEAP (Ustaw rozmiar stosu)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Uwagi

Opcja/HEAP ustawia rozmiar sterty w bajtach. Ta opcja jest używana tylko podczas kompilowania pliku. exe.

Argument *rezerwy* określa całkowitą alokację sterty w pamięci wirtualnej. Domyślny rozmiar sterty wynosi 1 MB. Konsolidator zaokrągla określoną wartość do najbliższej 4 bajtów.

Opcjonalny `commit` argument określa ilość pamięci fizycznej do przydzielenia w danym momencie. Przydzielona pamięć wirtualna powoduje, że miejsce jest zarezerwowane w pliku stronicowania. Wyższa `commit` wartość umożliwia zaoszczędzenie czasu, gdy aplikacja wymaga większej liczby miejsc sterty, ale zwiększa wymagania dotyczące pamięci i prawdopodobnie czasu uruchamiania.

Określ *rezerwę* i `commit` wartości w notacji dziesiętnej lub w języku C.

Ta funkcja jest również dostępna za pośrednictwem pliku definicji modułu z [heapsize](heapsize.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **systemu** .

1. Zmodyfikuj właściwość **rozmiar zatwierdzenia sterty** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> i <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A> .

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
