---
description: Dowiedz się więcej o:/ALIGN (wyrównanie sekcji)
title: /ALIGN (Wyrównanie sekcji)
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: d8a9af473252a2eff8957c5d2b4c54c7f7c862aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187263"
---
# <a name="align-section-alignment"></a>/ALIGN (Wyrównanie sekcji)

## <a name="syntax"></a>Składnia

> **/Align**[**:**_Number_]

### <a name="arguments"></a>Argumenty

*Liczba*<br/>
Wartość wyrównania w bajtach.

## <a name="remarks"></a>Uwagi

Opcja **/align** określa wyrównanie każdej sekcji w liniowej przestrzeni adresowej programu. Argument *Number* jest w bajtach i musi być potęgą liczby 2. Wartość domyślna to 4K (4096). Konsolidator emituje ostrzeżenie, jeśli wyrównanie generuje nieprawidłowy obraz.

Jeśli nie piszesz aplikacji, takiej jak sterownik urządzenia, nie trzeba modyfikować wyrównania.

Istnieje możliwość zmodyfikowania wyrównania określonej sekcji za pomocą parametru align do opcji [/Section](section-specify-section-attributes.md) .

Określona wartość wyrównania nie może być mniejsza niż największe wyrównanie sekcji.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. Wprowadź opcję w polu **dodatkowe opcje** . Wybierz **przycisk OK** lub **Zastosuj** , aby zastosować zmianę.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
