---
description: Dowiedz się więcej o:/FM (nazwa Mapfile)
title: /Fm (Nazwa Mapfile)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: 5c86a18ae9880a499997bcac2d8411859753d858
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200484"
---
# <a name="fm-name-mapfile"></a>/Fm (Nazwa Mapfile)

Nakazuje konsolidatorowi utworzenie mapfile zawierającego listę segmentów w kolejności, w jakiej występują w odpowiednim pliku exe lub DLL.

## <a name="syntax"></a>Składnia

```
/Fmpathname
```

## <a name="remarks"></a>Uwagi

Domyślnie mapfile otrzymuje podstawową nazwę odpowiedniego pliku źródłowego C lub C++ z. Rozszerzenie mapy.

Określenie **/FM** ma taki sam skutek jak w przypadku wybrania opcji konsolidatora [/map (Generate Mapfile)](map-generate-mapfile.md) .

Jeśli określisz [/c (Kompiluj bez konsolidacji)](c-compile-without-linking.md) , aby pominąć konsolidację, **/FM** nie ma wpływu.

Symbole globalne w mapfile zazwyczaj mają jeden lub więcej wiodących podkreśleń, ponieważ kompilator dodaje wiodący znak podkreślenia do nazw zmiennych. Wiele symboli globalnych, które pojawiają się w mapfile, są używane wewnętrznie przez kompilator i biblioteki standardowe.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[Określanie nazwy ścieżki](specifying-the-pathname.md)
