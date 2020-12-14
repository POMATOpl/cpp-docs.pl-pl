---
description: Dowiedz się więcej na temat:/DEBUGTYPE (opcje debugowania informacji)
title: /DEBUGTYPE (opcje informacji debugowania)
ms.date: 11/04/2016
f1_keywords:
- /debugtype
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
ms.openlocfilehash: 858d5ed8eb449931229700a10b755dd61ef371cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201732"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (opcje informacji debugowania)

Opcja/DEBUGTYPE określa typy informacji debugowania generowanych przez opcję/DEBUG.

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>Argumenty

**CV**<br/>
Informuje konsolidator, aby wyemituje informacje debugowania dotyczące symboli, numerów wierszy i innych informacji o kompilacji obiektu w pliku PDB. Domyślnie ta opcja jest włączona, gdy wartość **/Debug** jest określona i nie określono **/DEBUGTYPE** .

**PDATA**<br/>
Nakazuje konsolidatorowi Dodawanie wpisów. pdata i. xdata do informacji o strumieniu debugowania w pliku PDB. Domyślnie ta opcja jest włączona, gdy określono obie opcje **/Debug** i  /+. Jeśli **/DEBUGTYPE: pData** jest określony przez siebie, konsolidator automatycznie zawiera symbole debugowania w pliku PDB. Jeśli **/DEBUGTYPE: PDATA, NAprawianie** nie obejmuje symboli debugowania w pliku PDB.

**PRAWIANIE**<br/>
Nakazuje konsolidatorowi Dodawanie wpisów tabeli relokacji do informacji o strumieniu debugowania w pliku PDB. Domyślnie ta opcja jest włączona, gdy określono obie opcje **/Debug** i **/Profile** . Jeśli **/DEBUGTYPE: Naprawa** lub **/DEBUGTYPE: Naprawa, pData** jest określony, konsolidator nie obejmuje symboli debugowania w pliku PDB.

Argumenty do **/DEBUGTYPE** mogą być łączone w dowolnej kolejności, rozdzielając je przecinkami. W przypadku opcji **/DEBUGTYPE** i jej argumentów nie jest rozróżniana wielkość liter.

## <a name="remarks"></a>Uwagi

Użyj opcji **/DEBUGTYPE** , aby określić dołączenie danych tabeli relokacji lub informacji nagłówka. pdata i. xdata w strumieniu debugowania. Powoduje to, że konsolidator dołącza informacje o kodzie trybu użytkownika widocznym w debugerze jądra w przypadku przerwania w kodzie trybu jądra. Aby symbole debugowania były dostępne po określeniu **poprawki** , należy uwzględnić argument **OKS** .

Aby debugować kod w trybie użytkownika, który jest typowy dla aplikacji, opcja **/DEBUGTYPE** nie jest wymagana. Domyślnie przełączniki kompilatora, które określają dane wyjściowe debugowania ([/Z7,/Zi,/Zi](z7-zi-zi-debug-information-format.md)) emitują wszystkie informacje wymagane przez debuger programu Visual Studio. Użyj **/DEBUGTYPE: pData** lub **/DEBUGTYPE: CV, PDATA, naprawa** do debugowania kodu, który łączy składniki trybu użytkownika i trybu jądra, takie jak aplikacja konfiguracyjna sterownika urządzenia. Aby uzyskać więcej informacji na temat debugerów trybu jądra, zobacz [narzędzia debugowania dla systemu Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)

## <a name="see-also"></a>Zobacz też

[/DEBUG (generowanie informacji o debugowaniu)](debug-generate-debug-info.md)<br/>
[/Sterownika systemu Windows NT.](driver-windows-nt-kernel-mode-driver.md)<br/>
[/PROFILE (Profiler narzędzi do oceny wydajności)](profile-performance-tools-profiler.md)<br/>
[Narzędzia debugowania dla systemu Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)
