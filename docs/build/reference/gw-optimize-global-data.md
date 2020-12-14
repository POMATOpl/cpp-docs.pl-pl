---
description: Dowiedz się więcej o:/GW (Optymalizuj dane globalne)
title: /Gw (Optymalizuj dane globalne)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 2f9a6b9452f09473e650a5453ad2600cc73f0c00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200146"
---
# <a name="gw-optimize-global-data"></a>/Gw (Optymalizuj dane globalne)

Dane globalne pakietu w sekcjach COMDAT na potrzeby optymalizacji.

## <a name="syntax"></a>Składnia

```
/Gw[-]
```

## <a name="remarks"></a>Uwagi

Opcja **/GW** powoduje, że kompilator pakuje dane globalne w poszczególnych sekcjach COMDAT. Domyślnie **/GW** jest wyłączony i musi być jawnie włączony. Aby jawnie ją wyłączyć, użyj **/GW-**. Gdy włączone są zarówno **/GW** , jak i [/GL](gl-whole-program-optimization.md) , konsolidator korzysta z optymalizacji całego programu, aby porównać sekcje COMDAT w wielu plikach obiektów w celu wykluczenia danych globalnych niezwiązanych z odwołaniami lub scalenia identycznych danych globalnych tylko do odczytu. Może to znacznie zmniejszyć rozmiar wynikowego binarnego pliku wykonywalnego.

Gdy kompilujesz i łączsz oddzielnie, możesz użyć opcji konsolidatora [/OPT: ref](opt-optimizations.md) , aby wykluczyć z pliku wykonywalnego dane globalne, które nie są używane w plikach obiektów skompilowanych za pomocą opcji **/GW** .

Można również użyć opcji konsolidatora [/OPT: ICF](opt-optimizations.md) i [/LTCG](ltcg-link-time-code-generation.md) , aby scalić w pliku wykonywalnym wszystkie identyczne dane globalne tylko do odczytu dla wielu plików obiektów skompilowanych przy użyciu opcji **/GW** .

Aby uzyskać więcej informacji, zobacz [wprowadzenie do przełącznika kompilatora/GW](https://devblogs.microsoft.com/cppblog/introducing-gw-compiler-switch/) na blogu zespołu języka C++.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **C/C++** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby obejmowała **/GW** , a następnie wybierz **przycisk OK**.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
