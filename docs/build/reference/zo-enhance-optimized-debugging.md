---
description: Dowiedz się więcej na temat:/zo (rozszerzanie zoptymalizowanego debugowania)
title: /Zo (rozszerzanie zoptymalizowanego debugowania)
ms.date: 11/04/2016
f1_keywords:
- -Zo
- /Zo
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
ms.openlocfilehash: b2d5fb37205a6cf58492d7e6bc9080867ebacf54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224351"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (rozszerzanie zoptymalizowanego debugowania)

Generuj ulepszone informacje o debugowaniu dla zoptymalizowanego kodu w kompilacjach niedebugowania.

## <a name="syntax"></a>Składnia

```cpp
/Zo[-]
```

## <a name="remarks"></a>Uwagi

Przełącznik kompilatora **/zo** generuje ulepszone informacje o debugowaniu dla zoptymalizowanego kodu. Optymalizacja może używać rejestrów zmiennych lokalnych, zmiany kolejności kodu, pętli vectorize oraz wywołań funkcji wbudowanych. Optymalizacje mogą zasłaniać relacje między kodem źródłowym i skompilowanym kodem obiektu. Przełącznik **/zo** informuje kompilator w celu wygenerowania dodatkowych informacji o debugowaniu dla zmiennych lokalnych i funkcji zawartych w wierszu. Użyj go, aby zobaczyć zmienne w oknach **autostarts**, **locale** i **Watch** w przypadku przechodzenia przez zoptymalizowany kod w debugerze programu Visual Studio. Włącza również ślady stosu do wyświetlania funkcji wbudowanych w debugerze WinDBG. Kompilacje debugowania, które mają wyłączone optymalizacje ([/od](od-disable-debug.md)), nie potrzebują dodatkowych informacji o debugowaniu generowanych po określeniu **/zo** . Użyj przełącznika **/zo** , aby debugować konfiguracje wydań z włączoną optymalizacją. Aby uzyskać więcej informacji na temat przełączników optymalizacji, zobacz [/O opcje (Optymalizuj kod)](o-options-optimize-code.md). Opcja **/zo** jest domyślnie włączona w programie Visual Studio podczas określania informacji debugowania z **/Zi** lub **/Z7**. Określ **/zo-** , aby jawnie wyłączyć tę opcję kompilatora.

Przełącznik **/zo** jest dostępny w Visual Studio 2013 Update 3 i zastępuje wcześniej nieudokumentowany przełącznik **/d2Zi +** .

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Aby ustawić opcję kompilatora/zo w programie Visual Studio

1. Otwórz okno dialogowe **strony właściwości** dla projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz **Właściwości konfiguracji**, folder **C/C++** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby uwzględnić `/Zo` , a następnie wybierz przycisk **OK**.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/O opcje (Optymalizuj kod)](o-options-optimize-code.md)<br/>
[/Z7,/Zi,/ZI (format informacji o debugowaniu)](z7-zi-zi-debug-information-format.md)<br/>
[Edytuj i kontynuuj](/visualstudio/debugger/edit-and-continue)
