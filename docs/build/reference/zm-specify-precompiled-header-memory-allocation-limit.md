---
description: Dowiedz się więcej o:/zm (Określ limit alokacji pamięci prekompilowanego nagłówka)
title: /Zm (Określ limit alokacji pamięci prekompilowanego nagłówka)
ms.date: 03/08/2019
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: 624d8926961d9ca3d32ef204b70683c14dc3197f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224390"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Określ limit alokacji pamięci prekompilowanego nagłówka)

Określa ilość pamięci przydzielanej przez kompilator do konstruowania wstępnie skompilowanych nagłówków.

## <a name="syntax"></a>Składnia

```
/Zmfactor
```

## <a name="arguments"></a>Argumenty

*factor*<br/>
Czynnik skalowania określa ilość pamięci, której kompilator używa do konstruowania wstępnie skompilowanych nagłówków.

Argument *Factor* jest wartością procentową domyślnego rozmiaru buforu pracy zdefiniowanego przez kompilator. Wartością domyślną *czynnika* jest 100 (procent), ale można określić większe lub mniejsze kwoty.

## <a name="remarks"></a>Uwagi

W wersjach przed Visual Studio 2015 kompilator języka C++ użył kilku dyskretnych stert i każdy z nich miał ograniczony limit. Obecnie kompilator dynamicznie powiększa sterty zgodnie z potrzebami do całkowitego limitu rozmiaru sterty i zezwala prekompilowanym nagłówkowi na składanie wielu zakresów adresów. W związku z tym opcja kompilatora **/zm** jest rzadko niepotrzebna.

Jeśli kompilator wychodzi poza przestrzeń sterty i emituje komunikat o błędzie [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) podczas korzystania z opcji kompilatora **/zm** , może zaistnieć zbyt dużo pamięci. Rozważ usunięcie opcji **/zm** .

Jeśli kompilator emituje komunikat o błędzie [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) , towarzyszący komunikat [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) określa argument *Factor* do użycia podczas ponownej kompilacji przy użyciu opcji kompilatora **/zm** . Ten komunikat jest znaczący tylko w przypadku użycia prekompilowanego nagłówka `#pragma hdrstop` . W innych przypadkach jest to błąd fałszywe spowodowany problemami z pamięcią wirtualną systemu Windows, a zalecenia dotyczące używania opcji **/zm** powinny być ignorowane. Zamiast tego należy rozważyć zmniejszenie liczby procesów równoległych przy użyciu MSBUILD.EXE opcji **/maxcpucount** w połączeniu z opcją **/mp** , aby CL.EXE. Aby uzyskać więcej informacji, zobacz [artykuły prekompilowanego nagłówka (pch) i zalecenia](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

W poniższej tabeli przedstawiono sposób, w jaki argument *Factor* wpływa na limit alokacji pamięci, jeśli założono, że rozmiar domyślnego bufora prekompilowanego nagłówka to 75 MB.

|Wartość *czynnika*|Limit alokacji pamięci|
|-----------------------|-----------------------------|
|10|7,5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Inne sposoby ustawiania limitu alokacji pamięci

### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić opcję kompilatora /Zm w środowisku programistycznym Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. W okienku nawigacji wybierz pozycję **Właściwości konfiguracji**  >  **C/C++**  >  **wiersz polecenia**.

1. Wprowadź opcję kompilatora **/zm** w polu **dodatkowe opcje** .

### <a name="to-set-the-zm-compiler-option-programmatically"></a>Aby programowo ustawić opcję kompilatora /Zm

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
