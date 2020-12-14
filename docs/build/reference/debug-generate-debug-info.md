---
description: Dowiedz się więcej na temat:/DEBUG (generowanie informacji o debugowaniu)
title: /DEBUG (Generowanie informacji o debugowaniu)
ms.date: 05/16/2019
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
ms.openlocfilehash: b0ef30fe7cb5eb5af0c46d6f6a8f3533d2e7d6ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201823"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Generowanie informacji o debugowaniu)

```
/DEBUG[:{FASTLINK|FULL|NONE}]
```

## <a name="remarks"></a>Uwagi

Opcja **/Debug** tworzy informacje debugowania dla pliku wykonywalnego.

Konsolidator umieszcza informacje debugowania w pliku bazy danych programu (PDB). Aktualizuje plik PDB podczas kolejnych kompilacji programu.

Plik wykonywalny (exe lub DLL) utworzony na potrzeby debugowania zawiera nazwę i ścieżkę odpowiedniego pliku PDB. Debuger odczytuje osadzoną nazwę i używa pliku PDB podczas debugowania programu. Konsolidator używa podstawowej nazwy programu i rozszerzenia. pdb, aby nazwać bazę danych programu, i osadza ścieżkę, w której została utworzona. Aby zastąpić to ustawienie domyślne, należy ustawić [/PDB](pdb-use-program-database.md) i określić inną nazwę pliku.

Opcja **/Debug: Fastlink** jest dostępna w programie Visual Studio 2017 i nowszych. Ta opcja pozostawia prywatne informacje o symbolach w poszczególnych produktach kompilacji użytych do skompilowania pliku wykonywalnego. Generuje ograniczony plik PDB, który indeksuje informacje debugowania w plikach obiektów i bibliotekach używanych do kompilowania pliku wykonywalnego zamiast tworzenia pełnej kopii. Ta opcja umożliwia łączenie od dwóch do czterech razy jako szybkiej generacji plików PDB i jest zalecane w przypadku debugowania lokalnego i udostępnienia produktów kompilacji. Nie można użyć tego ograniczonego pliku PDB do debugowania, gdy wymagane produkty kompilacji są niedostępne, na przykład gdy plik wykonywalny jest wdrażany na innym komputerze. W wierszu polecenia dewelopera można użyć narzędzia mspdbcmf.exe do wygenerowania pełnego pliku PDB z tego ograniczonego pliku PDB. W programie Visual Studio Użyj elementów menu Projekt lub kompilacja do wygenerowania pełnego pliku PDB, aby utworzyć pełny plik PDB dla projektu lub rozwiązania.

Opcja **/Debug: Full** przenosi wszystkie informacje o symbolach prywatnych z poszczególnych produktów kompilacji (plików i bibliotek obiektów) do jednego pliku PDB i może być największą ilością czasochłonnych części linku. Jednak pełny PDB może służyć do debugowania pliku wykonywalnego, gdy nie są dostępne żadne inne produkty kompilacji, na przykład gdy plik wykonywalny jest wdrażany.

Opcja **/Debug: none** nie GENERUJE pliku PDB.

Po określeniu parametru **/Debug** bez dodatkowych opcji konsolidator domyślnie ustawia wartość **/Debug: Full** w przypadku kompilacji z wiersza polecenia i pliku reguł programu make, w przypadku kompilacji wydania w środowisku IDE programu Visual Studio oraz dla kompilacji w wersji Visual Studio 2015 i starszych. Począwszy od programu Visual Studio 2017, system kompilacji w środowisku IDE domyślnie ustawia wartość **/Debug: Fastlink** , gdy określisz opcję **/Debug** dla kompilacji debugowania. Inne wartości domyślne nie są zmieniane w celu zachowania zgodności z poprzednimi wersjami.

Opcja [C7 zgodna](z7-zi-zi-debug-information-format.md) przez kompilator (/Z7) powoduje, że kompilator pozostawia informacje debugowania w plikach. obj. Można również użyć opcji kompilatora [baza danych programu](z7-zi-zi-debug-information-format.md) (/ZI), aby przechowywać informacje o debugowaniu w PDB dla pliku. obj. Konsolidator szuka najpierw obiektu PDB w ścieżce bezwzględnej zapisaną w pliku. obj, a następnie w katalogu, który zawiera plik. obj. Nie można określić nazwy pliku PDB lub lokalizacji obiektu dla konsolidatora.

[/Incremental](incremental-link-incrementally.md) jest implikowane, gdy jest określony/Debug.

/DEBUG zmienia wartości domyślne dla opcji [/opt](opt-optimizations.md) z ref do NOREF i z zapory ICF na NOICF, dlatego jeśli chcesz użyć oryginalnych wartości domyślnych, należy jawnie określić/OPT: ref lub/OPT: ICF.

Nie można utworzyć pliku. exe lub. dll, który zawiera informacje debugowania. Informacje o debugowaniu są zawsze umieszczane w pliku obj lub PDB.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **debugowania** .

1. Zmodyfikuj właściwość **Generuj informacje o debugowaniu** , aby włączyć generowanie pliku PDB. Umożliwia to/DEBUG: FASTLINK domyślnie w programie Visual Studio 2017 i nowszych.

1. Zmodyfikuj właściwość **Generuj pełny plik bazy danych** , aby włączyć/Debug: Full dla pełnej generacji PDB dla każdej kompilacji przyrostowej.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
