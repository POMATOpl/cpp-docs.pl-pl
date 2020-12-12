---
description: Dowiedz się więcej o:/WX (Traktuj ostrzeżenia konsolidatora jako błędy)
title: /WX (Traktuj ostrzeżenia konsolidatora jak błędy)
ms.date: 11/04/2016
f1_keywords:
- /WX
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
ms.openlocfilehash: 965c48ff9c9f975350f3c1e54d8090823be8fd2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261037"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Traktuj ostrzeżenia konsolidatora jak błędy)

```
/WX[:NO]
```

## <a name="remarks"></a>Uwagi

/WX powoduje, że plik wyjściowy nie zostanie wygenerowany, jeśli konsolidator generuje ostrzeżenie.

Jest to podobne do **/WX** dla kompilatora (zobacz [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/we,/wo,/WV,/WX (poziom ostrzeżenia)](compiler-option-warning-level.md) , aby uzyskać więcej informacji. Jednak określenie **/WX** dla kompilacji nie oznacza, że **/WX** również będzie obowiązywać dla fazy linku; należy jawnie określić **/WX** dla każdego narzędzia.

Domyślnie **/WX** nie jest włączona. Aby traktować ostrzeżenia konsolidatora jako błędy, należy określić **/WX**. **/WX: No** jest taka sama jak nie określa **/WX**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję w polu **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
