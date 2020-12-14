---
description: Dowiedz się więcej o:/PDBALTPATH (Użyj alternatywnej ścieżki PDB)
title: /PDBALTPATH (Użyj alternatywnej ścieżki PDB)
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: f85a39fb4570773f01a98331e746f6b37b76c161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226067"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Użyj alternatywnej ścieżki PDB)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>Argumenty

*pdb_file_name*<br/>
Ścieżka i nazwa pliku. pdb.

## <a name="remarks"></a>Uwagi

Użyj tej opcji, aby podać alternatywną lokalizację pliku bazy danych programu (. pdb) w skompilowanym pliku binarnym. Zwykle konsolidator rejestruje lokalizację pliku. pdb w danych binarnych, które tworzy. Tej opcji można użyć, aby podać inną ścieżkę i nazwę pliku. pdb. Informacje zawarte w/PDBALTPATH nie zmieniają lokalizacji ani nazwy rzeczywistego pliku. pdb; zmienia informacje, które konsolidator zapisuje w pliku binarnym. Dzięki temu można podać ścieżkę, która jest niezależna od struktury plików komputera kompilacji. Dwa typowe zastosowania tej opcji to dostarczenie ścieżki sieciowej lub pliku bez informacji o ścieżce.

Wartość *pdb_file_name* może być dowolny ciąg, zmienna środowiskowa lub **% _PDB%**. Konsolidator będzie rozszerzał zmienną środowiskową, taką jak **% główny_katalog_systemowy%**, na wartość. Konsolidator definiuje zmienne środowiskowe **% _PDB%** i **% _EXT%**. **% _PDB%** powiększa się do nazwy pliku rzeczywistego pliku. pdb bez informacji o ścieżce i **% _EXT%** jest rozszerzeniem wygenerowanego pliku wykonywalnego.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)<br/>
[/PDBPATH](pdbpath.md)
