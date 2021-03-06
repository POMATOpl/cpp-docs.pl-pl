---
description: Dowiedz się więcej o:/Execution-charset (Ustaw zestaw znaków wykonywania)
title: /Execution-charset (Ustaw zestaw znaków wykonywania)
ms.date: 02/06/2019
f1_keywords:
- execution-charset
- /execution-charset
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
ms.openlocfilehash: 38d17ba1d7e73fa337c81cc0c54f0053bfcff2ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200822"
---
# <a name="execution-charset-set-execution-character-set"></a>/Execution-charset (Ustaw zestaw znaków wykonywania)

Umożliwia określenie zestawu znaków wykonywania dla pliku wykonywalnego.

## <a name="syntax"></a>Składnia

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Argumenty

*IANA_name*<br/>
Nazwa zestawu znaków zdefiniowanego przez organizację IANA.

*CPID*<br/>
Identyfikator strony kodowej.

## <a name="remarks"></a>Uwagi

Aby określić zestaw znaków wykonania, można użyć opcji **/Execution-charset** . Zestaw znaków wykonywania jest kodowaniem używanym dla tekstu programu, który jest danymi wejściowymi fazy kompilacji po wszystkich krokach przetwarzania wstępnego. Ten zestaw znaków jest używany do wewnętrznej reprezentacji dowolnego ciągu lub literału znakowego w skompilowanym kodzie. Ustaw tę opcję, aby określić zestaw znaków wykonania rozszerzonego, który ma być używany, gdy pliki źródłowe zawierają znaki, które nie są reprezentowane w podstawowym zestawie znaków wykonania. Aby określić zestaw znaków, który ma być używany, można użyć nazwy zestawu znaków IANA lub ISO albo kropki (.), a następnie cyfry od 3 do 5 cyfr dziesiętnego identyfikatora strony kodowej. Aby uzyskać listę obsługiwanych identyfikatorów stron kodowych i nazw zestawów znaków, zobacz [identyfikatory stron kodowych](/windows/win32/Intl/code-page-identifiers).

Domyślnie program Visual Studio wykrywa znacznik kolejności bajtów, aby określić, czy plik źródłowy jest w zakodowanym formacie Unicode, na przykład UTF-16 lub UTF-8. Jeśli nie zostanie znaleziony znacznik kolejności bajtów, zakłada, że plik źródłowy jest zakodowany przy użyciu bieżącej strony kodowej użytkownika, o ile nie określono nazwy zestawu znaków lub strony kodowej za pomocą opcji **określono element/source-charset** lub **/UTF-8** . Program Visual Studio umożliwia zapisanie kodu źródłowego C++ przy użyciu dowolnego z kilku kodowania znaków. Aby uzyskać informacje o zestawach znaków źródła i wykonania, zobacz [zestawy znaków](../../cpp/character-sets.md) w dokumentacji języka.

Jeśli chcesz ustawić zestaw znaków źródła i zestaw znaków wykonania na UTF-8, możesz użyć opcji kompilatora **/UTF-8** jako skrótu. Jest równoważne określeniu **określono element/source-charset: UTF-8/Execution-charset: UTF-8** w wierszu polecenia. Każda z tych opcji domyślnie włącza opcję **/Validate-charset** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji**, **C/C++**, folder **wiersza polecenia** .

1. W obszarze **Opcje dodatkowe** Dodaj opcję **/Execution-charset** i określ preferowane kodowanie.

1. Wybierz **przycisk OK** , aby zapisać zmiany.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[określono element/source-charset (Ustaw źródłowy zestaw znaków)](source-charset-set-source-character-set.md)<br/>
[/UTF-8 (Ustawianie źródłowych i wykonywalnych zestawów znaków na UTF-8)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Zweryfikuj zgodność znaków)](validate-charset-validate-for-compatible-characters.md)
