---
description: Dowiedz się więcej o:/SECTION (Określ atrybuty sekcji)
title: /SECTION (Określ atrybuty sekcji)
ms.date: 12/29/2017
f1_keywords:
- /section
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.openlocfilehash: 8731f720e04ae2893f288e4b96aeaa019af43350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224793"
---
# <a name="section-specify-section-attributes"></a>/SECTION (Określ atrybuty sekcji)

> **/Section:**_Nazwa_[[**!**] {**DEKPRSW**}] [**, Align =**_Number_]

## <a name="remarks"></a>Uwagi

Opcja **/Section** zmienia atrybuty sekcji, zastępując atrybuty ustawione, gdy plik. obj sekcji został skompilowany.

*Sekcja* w przenośnym pliku wykonywalnym (PE) jest nazwanym ciągłym blokiem pamięci, który zawiera kod lub dane. Niektóre sekcje zawierają kod lub dane, które program deklaruje i używa bezpośrednio, podczas gdy inne sekcje danych są tworzone przez konsolidatora i Menedżera bibliotek (lib.exe) i zawierają informacje istotne dla systemu operacyjnego. Aby uzyskać więcej informacji, zobacz [Format PE](/windows/win32/Debug/pe-format).

Określ dwukropek (:) i *Nazwa* sekcji. *Nazwa* uwzględnia wielkość liter.

Nie używaj następujących nazw, ponieważ powodują konflikt z nazwami standardowymi. Na przykład. sdata jest używany na platformach RISC:

- . Arch

- . BSS

- . dane

- .edata

- .idata

- . pdata

- . RDATA

- . reloc

- . RSRC

- . sbss

- . sdata

- .srdata

- . Text

- . xdata

Określ jeden lub więcej atrybutów dla sekcji. W poniższych znakach atrybutów nie jest rozróżniana wielkość liter. Należy określić wszystkie atrybuty, które ma mieć sekcja; pominięty znak atrybutu powoduje wyłączenie bitu atrybutu. Jeśli nie określisz języka R, W lub E, istniejący stan odczytu, zapisu lub pliku wykonywalnego pozostaje niezmieniony.

Aby Negate atrybut, poprzedź go znakiem wykrzyknika (!). W tej tabeli przedstawiono znaczenie znaków atrybutów:

|Znak|Atrybut|Znaczenie|
|---------------|---------------|-------------|
|E|Wykonaj polecenie|Sekcja jest plikiem wykonywalnym|
|R|Odczyt|Zezwala na operacje odczytu danych|
|W|Zapisywanie|Zezwala na operacje zapisu w danych|
|S|Udostępniona|Udostępnia sekcję wśród wszystkich procesów, które ładują obraz|
|D|Odrzucanie|Oznacza sekcję jako odrzucony|
|K|Podlega buforowaniu|Oznacza sekcję jako niebędącą w pamięci podręcznej|
|P|Stronicowalnej|Oznacza sekcję jako niestronicowaną|

K i P są nietypowe w tym, że flagi sekcji, które odpowiadają, są używane w sensie ujemnym. Jeśli określisz jeden z nich w sekcji Text przy użyciu opcji **/Section:. text, K** , nie ma żadnych różnic w flagach sekcji po uruchomieniu [polecenia DUMPBIN](dumpbin-options.md) z opcją [/Headers](headers.md) ; Sekcja została już niejawnie buforowana. Aby usunąć wartość domyślną, należy określić **/Section:. text,! K** zamiast. POLECENIA DUMPBIN ujawnia charakterystykę sekcji, w tym "nie w pamięci podręcznej".

Sekcja w pliku PE, która nie ma zestawu E, R lub W, jest prawdopodobnie nieprawidłowa.

Argument **align =**_Number_ pozwala określić wartość wyrównania dla określonej sekcji. Argument _Number_ jest w bajtach i musi być potęgą liczby 2. Aby uzyskać więcej informacji, zobacz [/align](align-section-alignment.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. Wprowadź opcję w polu **dodatkowe opcje** . Wybierz **przycisk OK** lub **Zastosuj** , aby zastosować zmianę.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
