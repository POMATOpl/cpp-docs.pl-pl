---
description: Dowiedz się więcej o:/SUBSYSTEM (Określ podsystem)
title: /SUBSYSTEM (Określ podsystem)
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: 18a8ad549cc4aa1e143e43619d549c9eb7ae7324
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236246"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (Określ podsystem)

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>Argumenty

**BOOT_APPLICATION**<br/>
Aplikacja działająca w środowisku rozruchu systemu Windows. Aby uzyskać więcej informacji na temat aplikacji rozruchowych, zobacz [Informacje o danych konfiguracji](/previous-versions/windows/desktop/bcd/about-bcd)rozruchu.

**KONSOLI**<br/>
Aplikacja w trybie znakowym Win32. System operacyjny udostępnia konsolę aplikacji konsolowych. Jeśli `main` lub `wmain` jest zdefiniowany dla kodu natywnego, `int main(array<String ^> ^)` jest zdefiniowany dla kodu zarządzanego lub można utworzyć aplikację w całości przy użyciu `/clr:safe` konsoli programu.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Podsystemy Extensible Firmware Interface. Aby uzyskać więcej informacji, zobacz specyfikację interfejsu EFI. Przykłady można znaleźć w witrynie sieci Web firmy Intel. Minimalna wersja i wersja domyślna to 1,0.

**TRYBU**<br/>
Sterowniki trybu jądra dla systemu Windows NT. Ta opcja jest zwykle zarezerwowana dla składników systemu Windows. Jeśli [jest określony wartość parametru](driver-windows-nt-kernel-mode-driver.md) //lub, natywny jest tryb macierzysty.

**POSIX**<br/>
Aplikacja uruchamiana z podsystemem POSIX w systemie Windows NT.

**Systemy**<br/>
Aplikacja nie wymaga konsoli, prawdopodobnie dlatego, że tworzy własne okna do interakcji z użytkownikiem. Jeśli `WinMain` lub `wWinMain` jest zdefiniowany dla kodu natywnego lub `WinMain(HISTANCE *, HINSTANCE *, char *, int)` `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` jest zdefiniowany dla kodu zarządzanego, domyślnie jest to system Windows.

*Główne* i *pomocnicze*<br/>
Obowiązkowe Określ minimalną wymaganą wersję podsystemu. Argumenty są liczbami dziesiętnymi z zakresu od 0 do 65 535. Aby uzyskać więcej informacji, zobacz uwagi. Brak górnych granic dla numerów wersji.

## <a name="remarks"></a>Uwagi

Opcja **/Subsystem** określa środowisko dla pliku wykonywalnego.

Wybór podsystemu wpływa na symbol punktu wejścia (lub funkcję punktu wejścia), który zostanie wybrany przez konsolidator.

Opcjonalne minimalne i domyślne numery wersji *głównych* i *pomocniczych* dla podsystemów są następujące.

|Wykonawc|Minimum|Domyślny|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|KONSOLI|5,01 (x86) 5,02 (x64) 6,02 (ARM)|6,00 (x86, x64) 6,02 (ARM)|
|Systemy|5,01 (x86) 5,02 (x64) 6,02 (ARM)|6,00 (x86, x64) 6,02 (ARM)|
|NATYWNy (z STEROWNIKIem: WDM)|1,00 (x86) 1,10 (x64, ARM)|1,00 (x86) 1,10 (x64, ARM)|
|NATYWNy (bez: WDM)|4,00 (x86) 5,02 (x64) 6,02 (ARM)|4,00 (x86) 5,02 (x64) 6,02 (ARM)|
|POSIX|1.0|19,90|
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder konsolidatora.

1. Wybierz stronę właściwości **systemu** .

1. Zmodyfikuj `SubSystem` Właściwość.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
