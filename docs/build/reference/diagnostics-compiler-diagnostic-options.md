---
description: Dowiedz się więcej o:/Diagnostics (opcje diagnostyki kompilatora)
title: /Diagnostics (opcje diagnostyki kompilatora)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 2c34edc0374e59720eb05e97379702833efaa703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201420"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/Diagnostics (opcje diagnostyki kompilatora)

Użyj opcji kompilatora **/Diagnostics** , aby określić wyświetlanie informacji o błędach i lokalizacji ostrzeżenia.

## <a name="syntax"></a>Składnia

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>Uwagi

Ta opcja jest obsługiwana w programie Visual Studio 2017 i nowszych.

Opcja kompilatora **/Diagnostics** kontroluje wyświetlanie informacji o błędach i ostrzeżeniach.

Opcja **/Diagnostics: klasyczny** jest wartością domyślną, która raportuje tylko numer wiersza, w którym znaleziono problem.

Opcja **/Diagnostics: Column** zawiera również kolumnę, w której znaleziono problem. Może to ułatwić zidentyfikowanie konkretnej konstrukcji językowej lub znaku, który jest przyczyną problemu.

Opcja **/Diagnostics: karetka** zawiera kolumnę, w której znaleziono problem i umieszcza karetkę (^) pod lokalizacją w wierszu kodu, w którym wykryto problem.

Należy zauważyć, że w niektórych przypadkach kompilator nie wykrywa problemu, który wystąpił. Na przykład nie można wykryć brakującego średnika, dopóki nie zostaną napotkane inne nieoczekiwane symbole. Kolumna jest raportowana, a karetka jest umieszczana w miejscu, w którym Kompilator wykrył, że coś było błędne, co nie zawsze jest konieczne do dokonania korekty.

Opcja **/Diagnostics** jest dostępna od programu Visual Studio 2017.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu.

1. W obszarze **Właściwości konfiguracji** rozwiń folder **C/C++** i wybierz stronę właściwości **Ogólne** .

1. Użyj kontrolki lista rozwijana w polu **Format diagnostyczny** , aby wybrać opcję wyświetlania diagnostyki. Wybierz **przycisk OK** lub **Zastosuj** , aby zapisać zmiany.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
