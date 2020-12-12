---
description: Dowiedz się więcej o:/DELAY (ustawienia opóźnienia importowania ładowania)
title: /DELAY (Ustawienia opóźnienia importowania ładowania)
ms.date: 11/04/2016
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
ms.openlocfilehash: f06a47280d563c138e184fdbdcdf033da705ce60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201524"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Ustawienia opóźnienia importowania ładowania)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Uwagi

Opcja/DELAY steruje [opóźnionym ładowaniem](linker-support-for-delay-loaded-dlls.md) bibliotek DLL:

- Kwalifikator UNLOAD informuje funkcję pomocnika ładowania opóźnień, aby obsługiwała jawne zwolnienie biblioteki DLL. Tabela adresów importu (IAT) jest resetowana do oryginalnej postaci, która unieważnia wskaźniki IAT i powoduje ich zastąpienie.

   Jeśli nie wybierzesz opcji ZWOLNIj, żadne wywołanie do [FUnloadDelayLoadedDLL](explicitly-unloading-a-delay-loaded-dll.md) zakończy się niepowodzeniem.

- Kwalifikator NOBIND informuje konsolidator, aby nie zawierał IAT możliwego do powiązania w końcowym obrazie. Wartość domyślna to utworzenie IAT możliwego do powiązania dla bibliotek DLL ładowanych z opóźnieniem. Obraz wyników nie może być powiązany statycznie. (Obrazy z IATsmi możliwymi do powiązania mogą być statycznie powiązane przed wykonaniem). Zobacz [/bind](bind.md).

   Jeśli biblioteka DLL jest powiązana, funkcja pomocnika podejmie próbę użycia informacji powiązanych zamiast wywoływania [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) dla każdego z przywoływanych importów. Jeśli sygnatura czasowa lub preferowany adres nie są zgodne z załadowanej biblioteki DLL, funkcja pomocnika przyjmuje, że powiązane IAT są nieaktualne i będą działać tak, jakby powiązane IAT nie istniały.

   NOBIND powoduje, że obraz programu jest większy, ale może skrócić czas ładowania biblioteki DLL. Jeśli nigdy nie zamierzasz powiązać biblioteki DLL, NOBIND uniemożliwi generowanie powiązanej IAT.

Aby określić biblioteki DLL do opóźnienia ładowania, użyj opcji [/DELAYLOAD](delayload-delay-load-import.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji**, **konsolidator**, a następnie wybierz pozycję **Zaawansowane**.

1. Zmodyfikuj właściwość **dll załadowanej z opóźnieniem** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
