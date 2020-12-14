---
description: 'Dowiedz się więcej o: łączenie danych wyjściowych'
title: Dane wyjściowe LINK
ms.date: 11/04/2016
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 18d14fda2702e588f69c8a613783087895827826
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190994"
---
# <a name="link-output"></a>Dane wyjściowe LINK

Łącza dane wyjściowe obejmują pliki exe, DLL, mapfiles i komunikaty.

## <a name="output-files"></a><a name="_core_output_files"></a> Pliki wyjściowe

Domyślny plik wyjściowy z LINKu jest plikiem exe. Jeśli opcja [/dll](dll-build-a-dll.md) jest określona, link kompiluje plik. dll. Można kontrolować nazwę pliku wyjściowego przy użyciu [nazwy pliku wyjściowego (/out)](out-output-file-name.md) .

W trybie przyrostowym LINK tworzy plik. ilk, aby przechowywać informacje o stanie dla późniejszych kompilacji przyrostowych programu. Aby uzyskać szczegółowe informacje na temat plików. ilk, zobacz [pliki. ilk](dot-ilk-files-as-linker-input.md). Aby uzyskać więcej informacji na temat konsolidacji przyrostowej, zobacz [link przyrostowo (/Incremental)](incremental-link-incrementally.md) .

Gdy LINK tworzy program, który zawiera eksport (zazwyczaj jest to biblioteka DLL), również kompiluje plik. lib, chyba że plik EXP został użyty w kompilacji. Nazwa pliku biblioteki importu można kontrolować za pomocą opcji [/IMPLIB](implib-name-import-library.md) .

Jeśli opcja [Generuj mapfile (/map)](map-generate-mapfile.md) jest określona, link tworzy mapfile.

Jeśli zostanie określona opcja [Generuj informacje o debugowaniu (/Debug)](debug-generate-debug-info.md) , link tworzy plik PDB, aby zawierał informacje o debugowaniu dla programu.

## <a name="other-output"></a><a name="_core_other_output"></a> Inne dane wyjściowe

Gdy wpiszesz `link` bez żadnych innych danych wejściowych wiersza polecenia, link wyświetla instrukcję użycia podsumowującą jej opcje.

LINK powoduje wyświetlenie komunikatu o prawach autorskich i wersji oraz ECHA dane wejściowe w pliku polecenia, chyba że jest używana opcja [pomijania wiodącego startu (/nologo)](nologo-suppress-startup-banner-linker.md) .

Możesz użyć opcji [Drukuj komunikaty o postępie (/verbose)](verbose-print-progress-messages.md) , aby wyświetlić dodatkowe szczegóły dotyczące kompilacji.

Komunikaty o błędach i ostrzeżeniach w formularzu LNK *nnnn*. Ten prefiks błędu i zakres liczb są również używane przez LIB, polecenia DUMPBIN i polecenia EDITBIN.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
