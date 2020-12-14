---
description: Dowiedz się więcej o:/V (numer wersji)
title: /V (Numer wersji)
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 5025642d4ae30315d24754a7ee46268050cfb22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187055"
---
# <a name="v-version-number"></a>/V (Numer wersji)

Przestarzałe. Osadza ciąg tekstowy w pliku. obj.

## <a name="syntax"></a>Składnia

```
/Vstring
```

## <a name="arguments"></a>Argumenty

*parametry*<br/>
Ciąg określający numer wersji lub informacje o prawach autorskich, które mają być osadzone w pliku. obj.

## <a name="remarks"></a>Uwagi

Stringcan etykieta pliku. obj z numerem wersji lub informacją o prawach autorskich. Spacje lub znaki tabulacji muszą być ujęte w znaki podwójnego cudzysłowu ("), jeśli są częścią ciągu. Ukośnik odwrotny ( \\ ) musi poprzedzać wszelkie podwójne cudzysłowy, jeśli są częścią ciągu. Spacja między **/v** i `string` jest opcjonalna.

Możesz również użyć [komentarza (C/C++)](../../preprocessor/comment-c-cpp.md) z argumentem typu komentarza kompilatora, aby umieścić nazwę i numer wersji kompilatora w pliku. obj.

Opcja **/v** jest przestarzała począwszy od programu Visual Studio 2005; **/V** użyto głównie do obsługi kompilowania sterowników urządzeń wirtualnych (VxDs), a Kompilowanie VxDs nie jest już obsługiwane przez zestaw narzędzi Visual C++. Aby zapoznać się z listą przestarzałych opcji kompilatora, zobacz Opcje kompilatora **przestarzałe i usunięte** w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
