---
description: Dowiedz się więcej na temat:/ZS (tylko sprawdzanie składni)
title: /Zs (Sprawdzaj tylko składnię)
ms.date: 11/04/2016
f1_keywords:
- /zs
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
ms.openlocfilehash: a4f5e2227104003a637db1d921fd959ea0a11ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224299"
---
# <a name="zs-syntax-check-only"></a>/Zs (Sprawdzaj tylko składnię)

Instruuje kompilator, aby sprawdzał tylko składnię plików źródłowych w wierszu polecenia.

## <a name="syntax"></a>Składnia

```
/Zs
```

## <a name="remarks"></a>Uwagi

W przypadku korzystania z tej opcji nie są tworzone żadne pliki wyjściowe i komunikaty o błędach są zapisywane w standardowym wyjściu.

Opcja **/ZS** umożliwia szybkie znajdowanie i poprawianie błędów składni przed skompilowaniem i połączeniem pliku źródłowego.

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
