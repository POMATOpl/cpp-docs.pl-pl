---
description: 'Dowiedz się więcej o: XDCMake Reference'
title: XDCMake — odwołanie
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: c9e597828ca37b67a21a5b2f442fffcac001b541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260998"
---
# <a name="xdcmake-reference"></a>XDCMake — odwołanie

xdcmake.exe jest programem, który kompiluje pliki. xdc do pliku. XML. Plik. xdc jest tworzony przez kompilator MSVC dla każdego pliku kodu źródłowego, gdy kod źródłowy jest kompilowany przy użyciu [/doc](doc-process-documentation-comments-c-cpp.md) i gdy plik kodu źródłowego zawiera komentarze dokumentacji oznaczone tagami XML.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Aby użyć xdcmake.exe w środowisku deweloperskim programu Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Otwórz folder **Właściwości konfiguracji** .

1. Kliknij stronę właściwości **Komentarze dokumentu XML** .

> [!NOTE]
> Opcje xdcmake.exe w wierszu polecenia różnią się od opcji, gdy xdcmake.exe jest używany w środowisku programistycznym (strony właściwości). Aby uzyskać informacje na temat używania xdcmake.exe w środowisku deweloperskim, zobacz [strony właściwości narzędzia Generator dokumentów XML](xml-document-generator-tool-property-pages.md).

## <a name="syntax"></a>Składnia

xdcmake `input_filename options`

## <a name="parameters"></a>Parametry

*input_filename*<br/>
Nazwa pliku. xdc używany jako dane wejściowe do xdcmake.exe. Określ jeden lub więcej plików. xdc lub użyj *. xdc, aby użyć wszystkich plików. xdc w bieżącym katalogu.

*Opcje*<br/>
Zero lub więcej z następujących elementów:

|Opcja|Opis|
|------------|-----------------|
|/?,/help|Wyświetl pomoc dla xdcmake.exe.|
|/Assembly:*filename*|Pozwala określić wartość \<assembly> tagu w pliku XML.  Domyślnie wartość \<assembly> tagu jest taka sama jak nazwa pliku. XML.|
|/nologo|Pomiń komunikat o prawach autorskich.|
|/out:*filename*|Pozwala określić nazwę pliku. XML.  Domyślnie nazwa pliku XML jest nazywana plikiem pierwszego pliku. xdc przetworzonym przez xdcmake.exe.|

## <a name="remarks"></a>Uwagi

Program Visual Studio będzie automatycznie wywoływał xdcmake.exe podczas kompilowania projektu. Możesz również wywołać xdcmake.exe w wierszu polecenia.

Zobacz [zalecane Tagi komentarzy dokumentacji](recommended-tags-for-documentation-comments-visual-cpp.md) , aby uzyskać więcej informacji na temat dodawania komentarzy do dokumentacji do plików kodu źródłowego.

## <a name="see-also"></a>Zobacz też

[Dokumentacja XML](xml-documentation-visual-cpp.md)
