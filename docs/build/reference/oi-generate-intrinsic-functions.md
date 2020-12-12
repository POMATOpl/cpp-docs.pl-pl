---
description: Dowiedz się więcej o:/Oi (Generuj funkcje wewnętrzne)
title: /Oi (Generuj funkcje wewnętrzne)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
ms.openlocfilehash: fc08ff495391092115197fe70e8c3673b77f32e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214282"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (Generuj funkcje wewnętrzne)

Zamienia niektóre wywołania funkcji na wewnętrzne lub w inny sposób specjalne formy funkcji, która ułatwia działanie aplikacji.

## <a name="syntax"></a>Składnia

```
/Oi[-]
```

## <a name="remarks"></a>Uwagi

Programy korzystające z funkcji wewnętrznych są szybsze, ponieważ nie mają narzutu wywołań funkcji, ale mogą być większe ze względu na dodatkowy utworzony kod.

Aby uzyskać więcej informacji o funkcjach, które mają wewnętrzne formularze, zobacz temat [wewnętrzna](../../preprocessor/intrinsic.md) .

**/Oi** to tylko żądanie do kompilatora, aby zastąpić niektóre wywołania funkcji z wewnętrznymi; Kompilator może wywołać funkcję (i nie zastąpić wywołania funkcji elementem wewnętrznym), jeśli spowoduje to lepszą wydajność.

**Specyficzne dla architektury x86**

Wewnętrzne funkcje zmiennoprzecinkowe nie wykonują żadnych specjalnych sprawdzeń na wartościach wejściowych i działają w ograniczonych zakresach danych wejściowych oraz mają różne wymagania dotyczące obsługi wyjątków i ograniczeń niż procedury biblioteki o tej samej nazwie. Korzystanie z prawdziwych form wewnętrznych oznacza utratę obsługi wyjątków IEEE oraz utratę `_matherr` i `errno` funkcjonalność; ta druga oznacza utratę zgodności z ANSI. Jednak formularze wewnętrzne mogą znacznie przyspieszyć programy intensywnie korzystające z liczby zmiennoprzecinkowej, a w przypadku wielu programów problemy ze zgodnością mają niewielki praktyczną wartość.

Można [użyć za pomocą opcji kompilatora,](za-ze-disable-language-extensions.md) aby zastąpić generowanie rzeczywistych wewnętrznych opcji zmiennoprzecinkowych. W takim przypadku funkcje są generowane jako procedury bibliotek, które przechodzą argumenty bezpośrednio do mikroukładu zmiennoprzecinkowego zamiast wypychania ich do stosu programu.

**ZAKOŃCZENIE specyficzne dla architektury x86**

Do tworzenia wewnętrznych funkcji lub [funkcji (C/C++)](../../preprocessor/function-c-cpp.md) można również użyć [wewnętrznych](../../preprocessor/intrinsic.md) , aby jawnie wymusić wywołanie funkcji.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **Optymalizacja** .

1. Zmodyfikuj właściwość **Włącz funkcje wewnętrzne** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.

## <a name="see-also"></a>Zobacz też

[/O opcje (Optymalizuj kod)](o-options-optimize-code.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[Funkcje wewnętrzne kompilatora](../../intrinsics/compiler-intrinsics.md)
