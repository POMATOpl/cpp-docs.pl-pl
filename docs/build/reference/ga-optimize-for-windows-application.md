---
description: Dowiedz się więcej o:/GA (Optymalizuj dla aplikacji systemu Windows)
title: /GA (Optymalizuj dla aplikacji systemu Windows)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: f9d65dce26e80b585abc4d67e2eef55f10cb365b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191982"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Optymalizuj dla aplikacji systemu Windows)

Wynikiem jest bardziej wydajny kod pliku. exe na potrzeby uzyskiwania dostępu do zmiennych magazynu wątków (TLS).

## <a name="syntax"></a>Składnia

```
/GA
```

## <a name="remarks"></a>Uwagi

**/Ga** przyspiesza dostęp do danych zadeklarowanych za pomocą [__declspec (thread)](../../cpp/declspec.md) w programie opartym na systemie Windows. Gdy ta opcja jest ustawiona, zakłada się, że makro [__tls_index](/windows/win32/ProcThread/thread-local-storage) ma wartość 0.

Użycie **/ga** dla biblioteki dll może spowodować nieprawidłowe generowanie kodu.

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
