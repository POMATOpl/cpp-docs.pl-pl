---
description: Dowiedz się więcej o:/bigobj (Zwiększ liczbę sekcji w. Plik obj)
title: /bigobj (Zwiększ ilość sekcji w pliku .Obj)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 4e820211ec46ad2a2d125552f95fb8a82c6f57ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182700"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Zwiększ ilość sekcji w pliku .Obj)

**/bigobj** zwiększa liczbę sekcji, które może zawierać plik obiektu.

## <a name="syntax"></a>Składnia

> **/bigobj**

## <a name="remarks"></a>Uwagi

Domyślnie plik obiektu może zawierać maksymalnie 65 279 (prawie 2 ^ 16) sekcji adresowane. Ten limit obowiązuje niezależnie od tego, która platforma docelowa została określona. **/bigobj** zwiększa pojemność adresu do 4 294 967 296 (2 ^ 32).

Większość modułów nigdy nie generuje pliku. obj, który zawiera więcej niż 65 279 sekcji. Jednak kod wygenerowany przez maszynę lub kod, który sprawia, że są duże użycie bibliotek szablonów, mogą wymagać plików. obj, które mogą zawierać więcej sekcji. **/bigobj** jest domyślnie włączona w projektach platforma uniwersalna systemu Windows (platformy UWP), ponieważ kod XAML wygenerowany przez maszynę zawiera dużą liczbę nagłówków. Jeśli wyłączysz tę opcję w projekcie aplikacji platformy UWP, kod może generować błąd kompilatora C1128.

Aby uzyskać informacje na temat formatu pliku. PE-COFF, zobacz [Format PE](/windows/win32/debug/pe-format) w dokumentacji systemu Windows.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Wprowadź opcję kompilatora **/bigobj** w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
