---
description: Dowiedz się więcej na temat:/Qfast_transcendentals (Wymuś szybkie Transcendentals)
title: /Qfast_transcendentals (Wymuszaj fast transcendentals)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 7701925aa7df33107b0829ade1c0c711eda14c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225664"
---
# <a name="qfast_transcendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Wymuszaj fast transcendentals)

Generuje kod wbudowany dla funkcji przestępną.

## <a name="syntax"></a>Składnia

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Uwagi

Ta opcja kompilatora wymusza konwersję funkcji przestępną na kod wbudowany, aby zwiększyć szybkość wykonywania. Ta opcja ma efekt tylko w przypadku sparowania z **/FP: except** lub **/FP: precyzyjne**. Generowanie kodu śródwierszowego dla funkcji przestępną jest już domyślnym zachowaniem w obszarze **/FP: Fast**.

Ta opcja jest niezgodna z **/FP: Strict**. Zobacz [/FP (Określ zachowanie Floating-Point)](fp-specify-floating-point-behavior.md) , aby uzyskać więcej informacji na temat opcji kompilatora zmiennoprzecinkowego.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/Q opcje (operacje na niskim poziomie)](q-options-low-level-operations.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
