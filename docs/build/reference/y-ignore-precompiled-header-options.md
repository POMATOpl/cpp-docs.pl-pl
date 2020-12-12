---
description: Dowiedz się więcej na temat:/Y-(Ignoruj opcje prekompilowanego nagłówka)
title: /Y- (Ignoruj opcje prekompilowanego nagłówka)
ms.date: 11/04/2016
f1_keywords:
- /y-
helpviewer_keywords:
- Y- compiler option [C++]
- -Y- compiler option [C++]
- /Y- compiler option [C++]
ms.assetid: cfaecb36-58db-46b8-b04d-cca6072b1b7a
ms.openlocfilehash: b3d1eb6d404e0463ee547c1905f792b485bf65f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260842"
---
# <a name="y--ignore-precompiled-header-options"></a>/Y- (Ignoruj opcje prekompilowanego nagłówka)

Powoduje, że wszystkie inne `/Y` Opcje kompilatora mają być ignorowane (i nie może zostać zastąpione).

## <a name="syntax"></a>Składnia

```
/Y-
```

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat prekompilowanych nagłówków, zobacz:

- [/Y (prekompilowane nagłówki)](y-precompiled-headers.md)

- [Wstępnie skompilowane pliki nagłówkowe](../creating-precompiled-header-files.md)

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
