---
description: Dowiedz się więcej na temat:/Validate-charset (Sprawdź pod kątem zgodności znaków)
title: /validate-charset (Zweryfikuj zgodność znaków)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: bda69c59fc89aae5028543ba579ee1e0b70f67e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250403"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (Zweryfikuj zgodność znaków)

Sprawdza, czy tekst pliku źródłowego zawiera tylko znaki do zaprezentowania jako UTF-8.

## <a name="syntax"></a>Składnia

```
/validate-charset[-]
```

## <a name="remarks"></a>Uwagi

Można użyć opcji **/Validate-charset** , aby sprawdzić, czy kod źródłowy zawiera tylko znaki, które mogą być reprezentowane zarówno w zestawie znaków źródłowych, jak i w zestawie znaków wykonania. To sprawdzenie jest włączane automatycznie po określeniu opcji kompilatora **określono element/source-charset**, **/Execution-charset** lub **/UTF-8** . Możesz jawnie wyłączyć ten test, określając opcję **/Validate-charset-** .

Domyślnie program Visual Studio wykrywa znacznik kolejności bajtów, aby określić, czy plik źródłowy jest w zakodowanym formacie Unicode, na przykład UTF-16 lub UTF-8. Jeśli nie zostanie znaleziony znacznik kolejności bajtów, zakłada, że plik źródłowy jest zakodowany przy użyciu bieżącej strony kodowej użytkownika, o ile nie określono strony kodowej za pomocą **/UTF-8** lub opcji **określono element/source-charset** . Program Visual Studio umożliwia zapisanie kodu źródłowego C++ przy użyciu dowolnego z kilku kodowania znaków. Aby uzyskać informacje o zestawach znaków źródła i wykonania, zobacz [zestawy znaków](../../cpp/character-sets.md) w dokumentacji języka. Aby uzyskać listę obsługiwanych identyfikatorów stron kodowych i nazw zestawów znaków, zobacz [identyfikatory stron kodowych](/windows/win32/Intl/code-page-identifiers).

Program Visual Studio używa kodowania UTF-8 podczas konwersji między zestawem znaków źródłowych a zestawem znaków wykonania. Jeśli w zestawie znaków wykonywania nie można przedstawić znaku w pliku źródłowym, konwersja UTF-8 zastępuje znak zapytania "?". Opcja **/Validate-charset** powoduje, że kompilacja zgłasza ostrzeżenie w przypadku wystąpienia tego problemu.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji**, **C/C++**, folder **wiersza polecenia** .

1. W obszarze **Opcje dodatkowe** Dodaj opcję **/Validate-charset** i określ preferowane kodowanie.

1. Wybierz **przycisk OK** , aby zapisać zmiany.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[/Execution-charset (Ustaw zestaw znaków wykonywania)](execution-charset-set-execution-character-set.md)<br/>
[określono element/source-charset (Ustaw źródłowy zestaw znaków)](source-charset-set-source-character-set.md)<br/>
[/UTF-8 (Ustawianie źródłowych i wykonywalnych zestawów znaków na UTF-8)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
