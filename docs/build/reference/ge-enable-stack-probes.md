---
description: Dowiedz się więcej o:/GE (Włącz sondy stosu)
title: /Ge (Włącz sondy stosu)
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: db996deb1c5b964661e5465fe72cfb0fab93df56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192021"
---
# <a name="ge-enable-stack-probes"></a>/Ge (Włącz sondy stosu)

Aktywuje sondy stosu dla każdego wywołania funkcji, które wymaga magazynu dla zmiennych lokalnych.

## <a name="syntax"></a>Składnia

```
/Ge
```

## <a name="remarks"></a>Uwagi

Ten mechanizm jest przydatny w przypadku ponownego zapisywania funkcji sondy stosu. Zaleca się użycie [/GH (Włącz funkcję Hook _penter)](gh-enable-penter-hook-function.md) zamiast ponownego zapisywania sondy stosu.

[/GS (kontrolowanie wywołań sprawdzania stosu)](gs-control-stack-checking-calls.md) ma ten sam efekt.

**/GE** jest przestarzała; począwszy od programu Visual Studio 2005, kompilator automatycznie generuje sprawdzanie stosu. Aby zapoznać się z listą przestarzałych opcji kompilatora, zobacz Opcje kompilatora **przestarzałe i usunięte** w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

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
