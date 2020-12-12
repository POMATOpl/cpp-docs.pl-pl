---
description: Dowiedz się więcej o:/NATVIS (Dodaj plik Natvis do pliku PDB)
title: /NATVIS (Dodaj Natvis do PDB)
ms.date: 08/10/2017
f1_keywords:
- /natvis
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: 7703915591a59a558c8580dd64b9be22d281d784
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190526"
---
# <a name="natvis-add-natvis-to-pdb"></a>/NATVIS (Dodaj Natvis do PDB)

> /NATVIS:*filename*

## <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Plik Natvis do dodania do pliku PDB. Osadza wizualizacje debugera w pliku Natvis do PDB.

## <a name="remarks"></a>Uwagi

Opcja/NATVIS osadza wizualizacje debugera zdefiniowane w pliku Natvis *filename* w pliku PDB wygenerowanym przez link. Dzięki temu debuger może wyświetlać wizualizacje niezależnie od pliku. Natvis. Można użyć wielu opcji/NATVIS do osadzenia więcej niż jednego pliku Natvis w wygenerowanym pliku PDB.

LINK ignoruje/NATVIS, gdy plik PDB nie jest tworzony przy użyciu opcji [/Debug](debug-generate-debug-info.md) . Aby uzyskać informacje na temat tworzenia i używania plików. Natvis, zobacz [Tworzenie niestandardowych widoków obiektów natywnych w debugerze programu Visual Studio](/visualstudio/debugger/create-custom-views-of-native-objects).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **wiersza polecenia** w folderze **konsolidatora** .

1. Dodaj opcję/NATVIS do pola tekstowego **Opcje dodatkowe** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Ta opcja nie ma programowego odpowiednika.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
