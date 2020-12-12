---
description: Dowiedz się więcej na temat:/GR (Włączanie informacji o typie Run-Time)
title: /GR (Włącz informacje typu Run-Time)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: 61b1a595999e5e00bf6b28c75be2de03467cc4ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200169"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Włącz informacje typu Run-Time)

Dodaje kod do sprawdzania typów obiektów w czasie wykonywania.

## <a name="syntax"></a>Składnia

```
/GR[-]
```

## <a name="remarks"></a>Uwagi

Gdy **/gr** jest włączona, kompilator definiuje `_CPPRTTI` makro preprocesora. Domyślnie **/gr** jest włączone. **/Gr-** wyłącza informacje o typie czasu wykonywania.

Użyj **/gr** , jeśli kompilator nie może statycznie rozpoznać typu obiektu w kodzie. Zwykle potrzebna jest opcja **/gr** , gdy kod używa [operatora dynamic_cast](../../cpp/dynamic-cast-operator.md) lub [typeid](../../cpp/typeid-operator.md). Jednak **/gr** zwiększa rozmiar sekcji obrazu. RDATA. Jeśli kod nie używa **`dynamic_cast`** lub **`typeid`** , **/gr-** może generować mniejszy obraz.

Aby uzyskać więcej informacji na temat sprawdzania typu w czasie wykonywania, zobacz [Informacje o typie czasu wykonywania](../../cpp/run-time-type-information.md) w *dokumentacji języka C++*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **języka** .

1. Zmodyfikuj właściwość **włącz Run-Time informacji o typie** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
