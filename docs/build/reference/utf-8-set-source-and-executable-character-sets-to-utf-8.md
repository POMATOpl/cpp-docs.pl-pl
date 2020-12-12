---
description: 'Dowiedz się więcej `/utf-8` na temat: (Ustawianie źródłowych i wykonywalnych zestawów znaków do UTF-8 )'
title: /UTF-8 (Ustaw źródłowe i wykonywalne zestawy znaków na UTF-8 )
ms.date: 04/26/2020
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
no-loc:
- UTF
- UTF-8
- UTF-16
ms.openlocfilehash: f9d58315a55d0e390ec07a1907af0befda127c54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176408"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-no-locutf-8"></a>`/utf-8` (Ustaw źródłowe i wykonywalne zestawy znaków na UTF-8 )

Określa zestaw znaków źródła i zestaw znaków wykonania jako UTF-8 .

## <a name="syntax"></a>Składnia

> **`/utf-8`**

## <a name="remarks"></a>Uwagi

Można użyć opcji, **`/utf-8`** Aby określić zestaw znaków źródła i wykonania jako zakodowany przy użyciu UTF-8 . Jest on równoznaczny z określeniem **`/source-charset:utf-8 /execution-charset:utf-8`** w wierszu polecenia. Każda z tych opcji również domyślnie włącza **`/validate-charset`** opcję. Aby uzyskać listę obsługiwanych identyfikatorów stron kodowych i nazw zestawów znaków, zobacz [identyfikatory stron kodowych](/windows/win32/Intl/code-page-identifiers).

Domyślnie program Visual Studio wykrywa znacznik kolejności bajtów, aby określić, czy plik źródłowy jest w zakodowanym formacie Unicode, na przykład UTF-16 czy UTF-8 . Jeśli nie zostanie znaleziony znacznik kolejności bajtów, zakłada, że plik źródłowy jest zakodowany przy użyciu bieżącej strony kodowej użytkownika, o ile nie określono strony kodowej za pomocą **`/utf-8`** lub **`/source-charset`** opcji. Program Visual Studio umożliwia zapisanie kodu źródłowego C++ przy użyciu dowolnego z kilku kodowania znaków. Aby uzyskać informacje o zestawach znaków źródła i wykonania, zobacz [zestawy znaków](../../cpp/character-sets.md) w dokumentacji języka.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Ustawianie opcji w programie Visual Studio lub programowo

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. W obszarze **Opcje dodatkowe** Dodaj **`/utf-8`** opcję, aby określić preferowane kodowanie.

1. Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[/Execution-charset (Ustaw zestaw znaków wykonywania)](execution-charset-set-execution-character-set.md)<br/>
[określono element/source-charset (Ustaw źródłowy zestaw znaków)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Zweryfikuj zgodność znaków)](validate-charset-validate-for-compatible-characters.md)
