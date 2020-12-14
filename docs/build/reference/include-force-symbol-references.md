---
description: Dowiedz się więcej o:/INCLUDE (Wymuszaj odwołania do symboli)
title: /INCLUDE (Wymuszaj odwołania do symboli)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 4938f5e92f91718f522df103303e6382005d463c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191306"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (Wymuszaj odwołania do symboli)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>Parametry

*symboliczn*<br/>
Określa symbol, który ma zostać dodany do tabeli symboli.

## <a name="remarks"></a>Uwagi

Opcja/INCLUDE informuje konsolidator, aby dodał określony symbol do tabeli symboli.

Aby określić wiele symboli, wpisz przecinek (,), średnik (;) lub spację między nazwami symboli. W wierszu polecenia określ/INCLUDE: `symbol` raz dla każdego symbolu.

Konsolidator rozpoznaje `symbol` przez dodanie obiektu, który zawiera definicję symbolu do programu. Ta funkcja jest przydatna do dołączania obiektu biblioteki, który w przeciwnym razie nie zostałby połączony z programem.

Określenie symbolu z tą opcją spowoduje zastąpienie usuwania tego symbolu przez [/OPT: ref](opt-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **dane wejściowe** .

1. Modyfikuj Właściwość **Force symbol References** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
