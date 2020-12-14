---
description: Dowiedz się więcej o:/Oy (pominięcie wskaźnika ramki)
title: /Oy (Pominięcie wskaźnika ramki)
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: dc0f9272bce5ad36840eac9ccdfc7e2465f7e3c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226301"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Pominięcie wskaźnika ramki)

Pomija tworzenie wskaźników ramek na stosie wywołań.

## <a name="syntax"></a>Składnia

> /Oy [-]

## <a name="remarks"></a>Uwagi

Ta opcja przyspiesza wywołania funkcji, ponieważ nie trzeba definiować i usuwać żadnych wskaźników ramek. Dodatkowo zwalnia jeszcze jeden rejestr do ogólnego użycia.

**/Oy** umożliwia pominięcie wskaźnika ramki i **/Oy-** powoduje wyłączenie pomijania. W kompilatorach x64, **/Oy** i **/Oy-** są niedostępne.

Jeśli kod wymaga adresowania opartego na ramce, można określić opcję **/Oy-** po opcji **/OX** lub użyć opcji [Optymalizuj](../../preprocessor/optimize.md) z argumentami "**y**" i **off** , aby uzyskać maksymalną optymalizację przy użyciu adresów opartych na ramce. Kompilator wykrywa większość sytuacji, w których wymagane jest adresowanie oparte na ramce (na przykład z `_alloca` `setjmp` funkcjami i z obsługą wyjątków strukturalnych).

[/OX (włączenie optymalizacji z największą szybkością)](ox-full-optimization.md) i [/O1,/O2 (Minimalizuj rozmiar, maksymalizuj szybkość)](o1-o2-minimize-size-maximize-speed.md) oznacza **/Oy**. Określenie **/Oy-** po opcji **/OX**, **/O1** lub **/O2** wyłącza **/Oy**, niezależnie od tego, czy jest to jawne czy implikowane.

Opcja kompilatora **/Oy** sprawia, że debuger jest trudniejszy, ponieważ kompilator pomija informacje o wskaźniku ramki. W przypadku określenia opcji kompilatora debugowania ([/Z7,/Zi,/Zi](z7-zi-zi-debug-information-format.md)) zaleca się określenie opcji **/Oy-** po dowolnych innych opcjach kompilatora optymalizacji.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości optymalizacji **C/C++** właściwości konfiguracji  >   .

1. Zmodyfikuj właściwość **pomijanie wskaźników ramki** . Ta właściwość dodaje lub usuwa tylko opcję **/Oy** . Jeśli chcesz dodać opcję **/Oy-** , wybierz stronę właściwości **wiersza polecenia** i zmodyfikuj **dodatkowe opcje**.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Zobacz też

[/O opcje (Optymalizuj kod)](o-options-optimize-code.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
