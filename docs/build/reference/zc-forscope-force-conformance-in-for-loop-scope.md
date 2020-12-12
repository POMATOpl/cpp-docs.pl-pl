---
description: 'Dowiedz się więcej o:/Zc: forScope (Wymuszaj zgodność w zakresie pętli for)'
title: /Zc:forScope (Wymuszaj zgodność w zakresie pętli For)
ms.date: 03/06/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
ms.openlocfilehash: 7124bba6608facfea546974cfa40ef9556ff713a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114666"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (Wymuszaj zgodność w zakresie pętli For)

Służy do implementowania standardowego zachowania języka C++ [dla pętli z](../../cpp/for-statement-cpp.md) rozszerzeniami Microsoft ([/ze](za-ze-disable-language-extensions.md)).

## <a name="syntax"></a>Składnia

> **/Zc: forScope**[ **-** ]

## <a name="remarks"></a>Uwagi

Standardowe zachowanie polega na **`for`** tym, że inicjator pętli wykracza poza zakres po **`for`** pętli. W obszarze **/Zc: forScope-** i [/ze](za-ze-disable-language-extensions.md), **`for`** inicjator pętli pozostaje w zakresie do momentu zakończenia zakresu lokalnego.

Opcja **/Zc: forScope** jest domyślnie włączona. **/Zc: forScope** nie ma zmian, jeśli określono opcję [/permissive-](permissive-standards-conformance.md) .

Opcja **/Zc: forScope-** Option jest przestarzała i zostanie usunięta w przyszłej wersji. Użycie elementu **/Zc: forScope —** generuje ostrzeżenie o zaniechaniu D9035.

Poniższy kod kompiluje się pod **/ze** , ale nie pod **/za**:

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

Jeśli używasz **/Zc: forScope-**, ostrzeżenie C4288 (domyślnie wyłączone) jest generowane, jeśli zmienna jest w zakresie z powodu deklaracji, która została utworzona w poprzednim zakresie. Aby to pokazać, Usuń `//` znaki z przykładowego kodu do zadeklarowania `int i` .

Możesz zmodyfikować zachowanie **/Zc: forScope** w czasie wykonywania za pomocą dyrektywy pragma [zgodności](../../preprocessor/conform.md) .

Jeśli używasz **/Zc: forScope —** w projekcie, który ma istniejący plik. PCH, zostanie wygenerowane ostrzeżenie, **/Zc: forScope-** jest ignorowana, a kompilacja jest kontynuowana przy użyciu istniejących plików. PCH. Jeśli chcesz wygenerować nowy plik PCH, użyj [/YC (Utwórz prekompilowany plik nagłówkowy)](yc-create-precompiled-header-file.md).

Aby uzyskać więcej informacji na temat problemów ze zgodnością w Visual C++, zobacz [niestandardowe zachowanie](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja języka **C/C++**  >   .

1. Zmodyfikuj **zgodność siły we właściwości zakresu pętli for** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.

## <a name="see-also"></a>Zobacz też

[/Zc (Zgodność)](zc-conformance.md)<br/>
[/Za,/ze (Wyłącz rozszerzenia językowe)](za-ze-disable-language-extensions.md)<br/>
