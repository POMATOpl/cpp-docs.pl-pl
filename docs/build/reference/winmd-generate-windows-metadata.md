---
description: Dowiedz się więcej na temat:/WINMD (generowanie metadanych systemu Windows)
title: /WINMD (generuj metadane systemu Windows)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
ms.openlocfilehash: 7cf52a49716e6ec30a29c7e6a96fe7a078b4830c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259087"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (generuj metadane systemu Windows)

Włącza generowanie pliku metadanych środowisko wykonawcze systemu Windows (WinMD).

> **/Winmd** \[ **:**{**no** \| }]

## <a name="arguments"></a>Argumenty

**/WINMD**<br/>
Ustawienie domyślne dla platforma uniwersalna systemu Windows aplikacji. Konsolidator generuje zarówno plik wykonywalny binarny, jak i plik metadanych WinMD.

**/WINMD: NIE**<br/>
Konsolidator generuje tylko plik wykonywalny binarny, ale nie plik WinMD.

**/WINMD: TYLKO**<br/>
Konsolidator generuje tylko plik. winmd, ale nie plik wykonywalny binarny.

## <a name="remarks"></a>Uwagi

Opcja konsolidatora **/winmd** jest używana dla aplikacji platformy UWP i składników środowiska uruchomieniowego systemu Windows w celu kontrolowania tworzenia pliku metadanych środowisko wykonawcze systemu Windows (WinMD). Plik. winmd jest rodzajem biblioteki DLL, która zawiera metadane dla typów środowiska wykonawczego systemu Windows i, w przypadku składników środowiska uruchomieniowego, implementacje tych typów. Metadane są zgodne ze standardem [ECMA-335](https://www.ecma-international.org/publications/standards/Ecma-335.htm) .

Domyślnie nazwa pliku wyjściowego ma postać *binaryname*. winmd. Aby określić inną nazwę pliku, należy użyć opcji [/WINMDFILE](winmdfile-specify-winmd-file.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja**  >  **konsolidator**  >  **okna właściwości metadanych** .

1. W polu listy rozwijanej **Generuj metadane systemu Windows** wybierz żądaną opcję.

## <a name="see-also"></a>Zobacz też

[Przewodnik: Tworzenie prostego składnika środowisko wykonawcze systemu Windows i wywoływanie go z JavaScript](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Wprowadzenie do Microsoft Interface Definition Language 3,0](/uwp/midl-3/intro)<br/>
[/WINMDFILE (Określ plik WinMD)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (Określ plik klucza winmd)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (Określ kontener klucza)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (częściowo Podpisz element winmd)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
