---
description: Dowiedz się więcej na temat:/FUNCTIONPADMIN (Tworzenie obrazu możliwy do poprawiania)
title: /FUNCTIONPADMIN (Utwórz obraz możliwy do poprawiania w trakcie działania)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: f86adb2001adacf1b6c8a03a90b7452505841c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192008"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Utwórz obraz możliwy do poprawiania w trakcie działania)

Przygotowuje obraz do poprawiania.

## <a name="syntax"></a>Składnia

> **/Functionpadmin**[**:**_Space_]

### <a name="arguments"></a>Argumenty

*spacje*<br/>
Ilość dopełnienia, która ma zostać dodana do początku każdej funkcji w bajtach. W przypadku procesora x86 ta wartość domyślna to 5 bajtów dopełnienia, a wartość domyślna to 6 bajtów. W przypadku innych elementów docelowych należy podać wartość.

## <a name="remarks"></a>Uwagi

Aby konsolidator mógł utworzyć obraz możliwy do poprawiania, pliki. obj muszą zostać skompilowane z [/hotpatch (Utwórz obraz możliwy do poprawiania)](hotpatch-create-hotpatchable-image.md).

Podczas kompilowania i łączenia obrazu z pojedynczym wywołaniem cl.exe, **/hotpatch** implikuje **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. Wprowadź opcję **/functionpadmin** w obszarze **Opcje dodatkowe**. Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
