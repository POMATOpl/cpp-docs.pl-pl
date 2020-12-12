---
description: Dowiedz się więcej o:/GZ (Włącz sprawdzanie błędów Run-Time ramki stosu)
title: /GZ (Włącz sprawdzanie błędów czasu wykonywania ramki stosu)
ms.date: 11/04/2016
f1_keywords:
- /gz
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
ms.openlocfilehash: 0b0936037c265bf57413c458ffc0a831184cb074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191696"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Włącz sprawdzanie błędów czasu wykonywania ramki stosu)

Wykonuje te same operacje co opcja [/RTC (sprawdzanie błędów czasu wykonywania)](rtc-run-time-error-checks.md) . Przestarzałe.

## <a name="syntax"></a>Składnia

```
/GZ
```

## <a name="remarks"></a>Uwagi

**/GZ** jest używany tylko w kompilacji niezoptymalizowanej ([/od (Disable)](od-disable-debug.md)).

**/GZ** jest przestarzała od programu Visual Studio 2005; Zamiast tego użyj [/RTC (sprawdzanie błędów czasu wykonywania)](rtc-run-time-error-checks.md) . Aby zapoznać się z listą przestarzałych opcji kompilatora, zobacz Opcje kompilatora **przestarzałe i usunięte** w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

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
