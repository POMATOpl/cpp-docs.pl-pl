---
description: Dowiedz się więcej na temat:/FD (nazwa pliku bazy danych programu)
title: /Fd (Nazwa pliku bazy danych programu)
ms.date: 11/04/2016
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
ms.openlocfilehash: 3990cdd6c560dfdeaef7078a29e965831c2a9504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200666"
---
# <a name="fd-program-database-file-name"></a>/Fd (Nazwa pliku bazy danych programu)

Określa nazwę pliku bazy danych programu (PDB) utworzonego za pomocą [/Z7,/Zi,/ZI (format informacji o debugowaniu)](z7-zi-zi-debug-information-format.md).

## <a name="syntax"></a>Składnia

```
/Fdpathname
```

## <a name="remarks"></a>Uwagi

Bez **/FD** nazwa pliku PDB domyślnie to VC *x* 0. pdb, gdzie *x* jest wersją główną Visual C++ w użyciu.

W przypadku określenia nazwy ścieżki, która nie zawiera nazwy pliku (ścieżka zostanie zakończona ukośnikiem odwrotnym), kompilator tworzy plik. pdb o nazwie VC *x* 0. pdb w określonym katalogu.

Jeśli określisz nazwę pliku, który nie zawiera rozszerzenia, kompilator używa. pdb jako rozszerzenie.

Ta opcja nazywa także plik State (. idb) używany do minimalnej kompilacji i kompilowania przyrostowego.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **pliki wyjściowe** .

1. Zmodyfikuj właściwość **Nazwa pliku bazy danych programu** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.

## <a name="example"></a>Przykład

Ten wiersz polecenia tworzy plik. pdb o nazwie programu MÓJ_PROG. pdb i pliku. IDB o nazwie IDB:

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[Określanie nazwy ścieżki](specifying-the-pathname.md)
