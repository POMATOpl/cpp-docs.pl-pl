---
description: Dowiedz się więcej na temat:/hotpatch (Tworzenie obrazu możliwy do poprawiania)
title: /hotpatch (Utwórz obraz możliwy do poprawiania w trakcie działania)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 2fc5fe629afcb1e721943b852c6f92351900ab7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199873"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Utwórz obraz możliwy do poprawiania w trakcie działania)

Przygotowuje obraz do stosowania poprawek na gorąco.

## <a name="syntax"></a>Składnia

```
/hotpatch
```

## <a name="remarks"></a>Uwagi

Gdy **/hotpatch** jest używany w kompilacji, kompilator zapewnia, że pierwsza instrukcja każdej funkcji wynosi co najmniej dwa bajty, co jest wymagane w przypadku stosowania poprawek na gorąco.

Aby ukończyć przygotowanie do tworzenia obrazu możliwy do poprawiania, po użyciu **/hotpatch** do skompilowania należy użyć [/functionpadmin (Utwórz obraz możliwy do poprawiania)](functionpadmin-create-hotpatchable-image.md) do połączenia. Podczas kompilowania i łączenia obrazu przy użyciu jednego wywołania cl.exe **/hotpatch** implikuje **/functionpadmin**.

Ponieważ instrukcje są zawsze dwa bajty lub większe w architekturze ARM, a kompilacja x64 jest zawsze traktowana jak w przypadku określenia **/hotpatch** , nie trzeba określać **/hotpatch** podczas kompilowania tych elementów docelowych. jednak nadal musisz połączyć się za pomocą **/functionpadmin** , aby utworzyć dla nich obrazy możliwy do poprawiania. Opcja kompilatora **/hotpatch** ma wpływ tylko na kompilację x86.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **C/C++** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Dodaj opcję kompilatora do pola **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
