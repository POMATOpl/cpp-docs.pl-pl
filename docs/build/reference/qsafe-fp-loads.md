---
description: Dowiedz się więcej na temat:/Qsafe_fp_loads
title: /Qsafe_fp_loads
ms.date: 01/24/2018
ms.openlocfilehash: e569b308d2da982c72775699ff2149daa45a8f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225521"
---
# <a name="qsafe_fp_loads"></a>/Qsafe_fp_loads

Wymaga instrukcji przenoszenia liczby całkowitej dla wartości zmiennoprzecinkowych i wyłącza pewne optymalizacje ładowania zmiennoprzecinkowego.

## <a name="syntax"></a>Składnia

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Uwagi

**/Qsafe_fp_loads** jest dostępna tylko w kompilatorach przeznaczonych dla architektury x86; nie jest on dostępny w kompilatorach przeznaczonych dla architektury x64 lub ARM.

**/Qsafe_fp_loads** wymusza użycie przez kompilator instrukcji przenoszenia liczb całkowitych zamiast zmiennoprzecinkowych instrukcji przenoszenia w celu przenoszenia danych między pamięcią a rejestrami MMX. Ta opcja wyłącza również funkcję Rejestruj optymalizację obciążenia dla wartości zmiennoprzecinkowych, które mogą być ładowane w wielu ścieżkach kontrolnych, gdy wartość może spowodować wyjątek podczas ładowania — na przykład wartość NaN.

Ta opcja jest zastępowana przez [/FP: except](fp-specify-floating-point-behavior.md). **/Qsafe_fp_loads** określa podzestaw zachowania kompilatora, który jest określony przez **/FP: z wyjątkiem**.

**/Qsafe_fp_loads** jest niezgodne z [/CLR](clr-common-language-runtime-compilation.md) i [/FP: Fast](fp-specify-floating-point-behavior.md). Aby uzyskać więcej informacji na temat opcji kompilatora zmiennoprzecinkowego, zobacz [/FP (Określ zachowanie Floating-Point)](fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Wprowadź opcję kompilatora w polu **dodatkowe opcje** . Wybierz **przycisk OK** , aby zastosować zmianę.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/Q opcje (operacje na niskim poziomie)](q-options-low-level-operations.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
