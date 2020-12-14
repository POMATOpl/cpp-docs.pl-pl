---
description: Dowiedz się więcej na temat:/STACK (alokacje stosu)
title: /STACK (Twórz stos z alokacji)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
ms.openlocfilehash: 6e74b508d8cdb2340c73360bf35272d9113a0f75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224469"
---
# <a name="stack-stack-allocations"></a>/STACK (Twórz stos z alokacji)

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Uwagi

Opcja/STACK ustawia rozmiar stosu w bajtach. Tej opcji należy użyć tylko w przypadku kompilowania pliku. exe.

`reserve`Wartość określa łączną alokację stosu w pamięci wirtualnej. W przypadku maszyn ARM, x86 i x64 rozmiar domyślnego stosu wynosi 1 MB.

`commit` podlega interpretacji przez system operacyjny. W systemie Windows Windows RT określa ilość pamięci fizycznej do przydzielenia w danym momencie. Przydzielona pamięć wirtualna powoduje, że miejsce jest zarezerwowane w pliku stronicowania. Wyższa `commit` wartość umożliwia zaoszczędzenie czasu, gdy aplikacja wymaga większej ilości miejsca na stosie, ale zwiększa wymagania dotyczące pamięci i prawdopodobnie czasu uruchamiania. W przypadku maszyn z procesorem ARM, x86 i x64 domyślna wartość zatwierdzenia to 4 KB.

Określ `reserve` wartości i `commit` w notacji dziesiętnej lub w języku C.

Innym sposobem ustawienia rozmiaru stosu jest instrukcja [STACKSIZE](stacksize.md) w pliku definicji modułu (. def). **STACKSIZE** zastępuje opcję alokacji stosu (/stack), jeśli oba są określone. Rozmiar stosu można zmienić po skompilowaniu pliku. exe przy użyciu narzędzia [polecenia EDITBIN](editbin-reference.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **systemu** .

1. Zmodyfikuj jedną z następujących właściwości:

   - **Rozmiar zatwierdzenia stosu**

   - **Rozmiar rezerwy stosu**

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> i <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> właściwości.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
