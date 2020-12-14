---
description: 'Dowiedz się więcej o:/FU (Nazwij plik wymuszony #using)'
title: '/FU (Nazwij wymuszone pliki dyrektywy #using)'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: 458369e7ff1322d2d2fa2fb37e8915c5a39c8446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200380"
---
# <a name="fu-name-forced-using-file"></a>/FU (Nazwij wymuszone pliki dyrektywy #using)

Opcja kompilatora, której można użyć jako alternatywy do przekazywania nazwy pliku do [dyrektywy #using](../../preprocessor/hash-using-directive-cpp.md) w kodzie źródłowym.

## <a name="syntax"></a>Składnia

>  *Plik* /Fu

## <a name="arguments"></a>Argumenty

*rozszerzeniem*<br/>
Określa plik metadanych, który ma zostać odwołany w tej kompilacji.

## <a name="remarks"></a>Uwagi

Przełącznik/FU przyjmuje tylko jedną nazwę pliku. Aby określić wiele plików, należy użyć/FU z każdym z nich.

Jeśli używasz języka C++/CLI i odwołują się do metadanych do używania funkcji [zaprzyjaźnionych zestawów](../../dotnet/friend-assemblies-cpp.md) , nie można użyć **/Fu**. Należy odwołać się do metadanych w kodzie za pomocą `#using` — wraz z `[as friend]` atrybutem. Przyjazne zestawy nie są obsługiwane w Visual C++ rozszerzenia składników C++/CX.

Aby uzyskać informacje dotyczące sposobu tworzenia zestawu lub modułu dla środowiska uruchomieniowego języka wspólnego (CLR), zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](clr-common-language-runtime-compilation.md). Aby uzyskać informacje o sposobach kompilowania w języku C++/CX, zobacz [Tworzenie aplikacji i bibliotek](../../cppcx/building-apps-and-libraries-c-cx.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja**  >    >  **zaawansowana** C/C++.

1. Zmodyfikuj właściwość **Force #using** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
