---
description: Dowiedz się więcej o:/homeparams (Kopiuj parametry rejestru do stosu)
title: /homeparams (Kopiuj parametry rejestru do stosu)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: 52145534121831be256c3db2a6ccacdffb30b2c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191475"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Kopiuj parametry rejestru do stosu)

Wymusza, aby parametry przesyłane w rejestrach były również zapisywane do ich lokalizacji na stosie przy wejściu do funkcji.

## <a name="syntax"></a>Składnia

> **/homeparams**

## <a name="remarks"></a>Uwagi

Ta opcja kompilatora jest dostępna tylko w kompilatorach natywnych i wielu, które są przeznaczone dla procesorów x64.

Konwencja wywoływania x64 wymaga przydzielenia przestrzeni stosu dla wszystkich parametrów, nawet w przypadku parametrów przewidzianych w rejestrach. Aby uzyskać więcej informacji, zobacz [przekazywanie parametrów](../../build/x64-calling-convention.md#parameter-passing). Domyślnie parametry rejestracji nie są kopiowane do przydzielonej przestrzeni stosowej w kompilacjach wydania. Utrudnia to debugowanie zoptymalizowanej kompilacji wydania programu.

W przypadku kompilacji wydania można użyć opcji **/homeparams** , aby wymusić, aby kompilator skopiował parametry rejestru do stosu, aby upewnić się, że można debugować aplikację. **/homeparams** jest przyczyną niekorzystnej wydajności, ponieważ wymaga dodatkowego cyklu do załadowania parametrów rejestru do stosu.

W kompilacjach debugowania stos jest zawsze wypełniany parametrami przekazaną w rejestrach.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Otwórz stronę właściwości **Konfiguracja**  >  wiersza polecenia **C/C++**  >   .

1. Wprowadź opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
