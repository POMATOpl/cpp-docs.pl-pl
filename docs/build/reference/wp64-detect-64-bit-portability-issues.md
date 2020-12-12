---
description: Dowiedz się więcej o:/Wp64 (Wykrywaj 64-bitowe problemy z przenośnością)
title: /Wp64 (Wykrywaj problemy związane z przenośnością w programowaniu 64-bitowym)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: d1ee441089531c4ebe222c73f6cec16b59fa7583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261089"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (Wykrywaj problemy związane z przenośnością w programowaniu 64-bitowym)

Ta opcja kompilatora jest przestarzała. W wersjach programu Visual Studio przed Visual Studio 2013 spowoduje to wykrycie problemów z przenośnością 64-bitowym na typach, które są również oznaczone słowem kluczowym [__w64](../../cpp/w64.md) .

## <a name="syntax"></a>Składnia

```
/Wp64
```

## <a name="remarks"></a>Uwagi

Domyślnie w wersjach programu Visual Studio przed Visual Studio 2013 opcja kompilatora **/Wp64** jest wyłączona w kompilatorze MSVC, który kompiluje 32-bitowy kod x86 i włączony w KOMPILATORze MSVC, który kompiluje 64-bitowy, kod x64.

> [!IMPORTANT]
> Opcja kompilatora [/Wp64](wp64-detect-64-bit-portability-issues.md) i słowo kluczowe [__w64](../../cpp/w64.md) są przestarzałe w programie Visual Studio 2010 i w programie Visual Studio 2012 i nie są obsługiwane, począwszy od Visual Studio 2013. W przypadku konwersji projektu korzystającego z tego przełącznika przełącznik nie zostanie zmigrowany podczas konwersji. Aby użyć tej opcji w programie Visual Studio 2010 lub Visual Studio 2012, należy wpisać przełącznik kompilatora w obszarze **Opcje dodatkowe** w sekcji **wiersz polecenia** właściwości projektu. Jeśli używasz opcji kompilatora **/Wp64** w wierszu polecenia, kompilator wystawia Command-Line ostrzeżenie D9002. Zamiast używać tej opcji i słowa kluczowego do wykrywania 64-bitowych problemów dotyczących przenośności, należy użyć kompilatora MSVC, który jest przeznaczony dla platformy 64-bitowej i określić opcję [/W4](compiler-option-warning-level.md) . Aby uzyskać więcej informacji, zobacz [Konfigurowanie projektów C++ dla 64-bitowych, docelowych dla procesorów x64](../configuring-programs-for-64-bit-visual-cpp.md).

Zmienne następujących typów są testowane w 32-bitowym systemie operacyjnym, tak jakby były używane w 64-bitowym systemie operacyjnym:

- int

- długi

- pointer

Jeśli regularnie kompilujesz aplikację przy użyciu kompilatora, który kompiluje 64-bitowy, kod x64, można po prostu wyłączyć **/Wp64** w kompilacjach 32-bitowych, ponieważ kompilator 64-bitowy wykrywa wszystkie problemy. Aby uzyskać więcej informacji na temat sposobu kierowania systemu operacyjnego Windows 64-bitowego, zobacz [Konfigurowanie projektów C++ dla 64-bitowych, elementów docelowych x64](../configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu.

   Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Zmodyfikuj **dodatkowe pole opcji** , aby uwzględnić **/Wp64**.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[Konfigurowanie projektów C++ dla 64-bitowych, docelowych procesorów x64](../configuring-programs-for-64-bit-visual-cpp.md)
