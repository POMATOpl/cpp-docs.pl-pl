---
description: Dowiedz się więcej na temat:/PDB (Korzystanie z bazy danych programu)
title: /PDB (Korzystaj z bazy danych programu)
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: 221d5d81dc3578e99751334b2e0a0a61aaaed356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226106"
---
# <a name="pdb-use-program-database"></a>/PDB (Korzystaj z bazy danych programu)

```
/PDB:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Nazwa określona przez użytkownika dla bazy danych programu (PDB), którą tworzy konsolidator. Zastępuje domyślną nazwę.

## <a name="remarks"></a>Uwagi

Domyślnie, gdy wartość [/Debug](debug-generate-debug-info.md) jest określona, konsolidator tworzy bazę danych programu (PDB), która przechowuje informacje debugowania. Domyślna nazwa pliku PDB ma nazwę podstawową programu i rozszerzenie. pdb.

Użyj/PDB:*filename* , aby określić nazwę pliku PDB. Jeśli/DEBUG nie jest określony, opcja/PDB jest ignorowana.

Plik PDB może mieć do 2 GB.

Aby uzyskać więcej informacji, zobacz [pliki. pdb jako dane wejściowe konsolidatora](dot-pdb-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **debugowania** .

1. Zmodyfikuj właściwość **Generuj plik bazy danych programu** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
