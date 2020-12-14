---
description: Dowiedz się więcej na temat:/FC (Pełna ścieżka pliku kodu źródłowego w diagnostyce)
title: /FC (Pełna ścieżka pliku kodu źródłowego w Diagnostyce)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 01d1148a32179a7c605a19dc7f2856b7697ae6fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200679"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Pełna ścieżka pliku kodu źródłowego w Diagnostyce)

Powoduje, że kompilator wyświetla pełną ścieżkę do plików kodu źródłowego przesłanych do kompilatora w diagnostyce.

## <a name="syntax"></a>Składnia

> /FC

## <a name="remarks"></a>Uwagi

Rozważmy następujący przykładowy kod:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Bez **/FC** tekst diagnostyczny będzie wyglądać podobnie do tego tekstu diagnostycznego:

- compiler_option_FC. cpp (5): błąd C2143: błąd składniowy: Brak znaku ";" przed "}"

W przypadku **/FC** tekst diagnostyczny będzie wyglądać podobnie do tego tekstu diagnostycznego:

- c:\test\ compiler_option_fc. cpp (5): błąd C2143: błąd składniowy: Brak znaku ";" przed "}"

**/FC** jest również potrzebna, jeśli chcesz zobaczyć pełną ścieżkę nazwy pliku przy użyciu makra &#95;&#95;pliku&#95;&#95; . Aby uzyskać więcej informacji na temat&#95;&#95; plików &#95;&#95;, zobacz [wstępnie zdefiniowane makra](../../preprocessor/predefined-macros.md) .

Opcja **/FC** jest implikowana przez **/Zi**. Aby uzyskać więcej informacji na temat **/Zi**, zobacz [/Z7,/Zi,/ZI (format informacji o debugowaniu)](z7-zi-zi-debug-information-format.md).

**/FC** wyprowadza pełne ścieżki w małych przypadkach.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja**  >    >  **zaawansowana** C/C++.

1. Zmodyfikuj właściwość **use Full Paths** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
