---
description: Dowiedz się więcej na temat:/INCREMENTAL (łączenie przyrostowe)
title: /INCREMENTAL (Łącz stopniowo)
ms.date: 11/04/2016
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
ms.openlocfilehash: 4b115bd88bed5b012c29c3d0e61d471aa869b78a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191293"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (Łącz stopniowo)

```
/INCREMENTAL[:NO]
```

## <a name="remarks"></a>Uwagi

Określa, jak konsolidator obsługuje łączenie przyrostowe.

Domyślnie konsolidator jest uruchamiany w trybie przyrostowym. Aby zastąpić domyślne łączenie przyrostowe, określ /INCREMENTAL:NO.

Program połączony przyrostowo jest funkcjonalnie równoważny programowi, który nie jest połączony przyrostowo. Jednak, ponieważ jest przygotowana do kolejnych łączy przyrostowych, przyrostowo połączonego pliku wykonywalnego, biblioteki statycznej lub biblioteki dołączanej dynamicznie:

- Jest większy niż program połączony nieprzyrostowo ze względu na dopełnienie kodu i danych. Dopełnienie umożliwia konsolidatorowi zwiększenie rozmiaru funkcji i danych bez konieczności ponownego tworzenia pliku.

- Może zawierać sekcje thunk skoków do obsługi przeniesienia funkcji do nowych adresów.

   > [!NOTE]
   > Aby upewnić się, że końcowa kompilacja wydania nie zawiera dopełnienia lub sekcje thunk, Połącz program nieprzyrostowo.

Aby łączyć przyrostowo, niezależnie od ustawienia domyślnego, określ /INCREMENTAL. Gdy ta opcja jest zaznaczona, konsolidator generuje ostrzeżenie, jeśli nie może połączyć się przyrostowo, a następnie łączy program nieprzyrostowo. Niektóre opcje i sytuacje zastępują /INCREMENTAL.

Większość programów może być łączonych przyrostowo. Jednak niektóre zmiany są zbyt duże, a niektóre opcje są niezgodne z łączeniem przyrostowym. Polecenie LINK wykonuje pełne połączenie, jeżeli jest określona którakolwiek z następujących opcji:

- Łączenie przyrostowe nie jest zaznaczone (/INCREMENTAL:NO)

- Wybrano /OPT:REF

- Wybrano /OPT:ICF

- Wybrano /OPT:LBR

- Wybrano /ORDER

/INCREMENTAL jest implikowane, gdy jest określony [/Debug](debug-generate-debug-info.md) .

Poza tym polecenie LINK wykonuje pełne połączenie, jeżeli wystąpi którakolwiek z następujących sytuacji:

- Brakuje pliku stanu przyrostowego (.ilk). (LINK tworzy nowy plik .ilk w ramach przygotowań do kolejnych łączeń przyrostowych).

- Nie ma uprawnienia do zapisu dla pliku .ilk. (LINK ignoruje plik. ilk i linki nie przyrostowo).

- Brakuje pliku wyjściowego .exe lub .dll.

- Sygnatura czasowa .ilk, .exe lub .dll została zmieniona.

- Opcja LINK została zmieniona. Większość opcji LINK po zmianie między kompilacjami powoduje pełne łącze.

- Plik obiektowy (.obj) jest dodawany lub pomijany.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **Ogólne** .

1. Zmodyfikuj właściwość **Włącz łączenie przyrostowe** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
