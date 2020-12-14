---
description: Dowiedz się więcej o:/PDBSTRIPPED (symbole prywatne)
title: /PDBSTRIPPED (Usuń symbole prywatne)
ms.date: 11/04/2016
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
ms.openlocfilehash: 27e70281ad12f4401ad6557ead9be11a38684472
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226041"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Usuń symbole prywatne)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>Argumenty

*pdb_file_name*<br/>
Nazwa określona przez użytkownika dla usuniętej bazy danych programu (PDB), którą tworzy konsolidator.

## <a name="remarks"></a>Uwagi

Opcja/PDBSTRIPPED tworzy drugi plik bazy danych (PDB) podczas kompilowania obrazu programu przy użyciu dowolnego z opcji kompilatora lub konsolidatora, które generują plik PDB ([/Debug](debug-generate-debug-info.md), [/Z7](z7-zi-zi-debug-information-format.md),/ZD lub/ZI). Ten drugi plik PDB pomija symbole, które nie powinny być wysyłane do klientów. Drugi plik PDB będzie zawierać tylko:

- Symbole publiczne

- Lista plików obiektów i fragmenty pliku wykonywalnego, do którego one współtworzą

- Rekordy debugowania optymalizacji wskaźnika ramki (FPO) używane do przechodzenia przez stos

Usunięty plik PDB nie będzie zawierał:

- Informacje o typie

- Informacje o numerze wiersza

- Symbole CodeView pliku dla obiektów, takie jak te dla funkcji, zmienne lokalne i dane statyczne

Pełny plik PDB będzie nadal generowany w przypadku użycia/PDBSTRIPPED.

Jeśli plik PDB nie zostanie utworzony,/PDBSTRIPPED jest ignorowany.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **debugowania** .

1. Modyfikuj Właściwość **symboli prywatnych paska** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
