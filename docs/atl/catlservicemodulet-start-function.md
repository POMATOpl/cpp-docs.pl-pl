---
description: 'Dowiedz się więcej o: Funkcja CAtlServiceModuleT:: Start — funkcja'
title: 'Funkcja CAtlServiceModuleT:: Start — funkcja'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: cfdae47f88c7957a4470da3129f3d3e071614276
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148320"
---
# <a name="catlservicemoduletstart-function"></a>Funkcja CAtlServiceModuleT:: Start — funkcja

Gdy usługa jest uruchomiona, `_tWinMain` wywołuje `CAtlServiceModuleT::WinMain` , co z kolei wywołuje `CAtlServiceModuleT::Start` .

`CAtlServiceModuleT::Start` konfiguruje tablicę `SERVICE_TABLE_ENTRY` struktur, które mapują poszczególne usługi do funkcji uruchamiania. Ta tablica jest następnie przenoszona do funkcji Win32 API, [StartServiceCtrlDispatcher](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw). Teoretycznie jeden plik EXE może obsłużyć wiele usług, a tablica może mieć wiele `SERVICE_TABLE_ENTRY` struktur. Obecnie jednak usługa wygenerowała ATL obsługuje tylko jedną usługę dla każdego pliku EXE. W związku z tym tablica zawiera pojedynczy wpis zawierający nazwę usługi i `_ServiceMain` funkcję uruchamiania. `_ServiceMain` jest statyczną funkcją składową, `CAtlServiceModuleT` która wywołuje niestatyczną funkcję członkowską `ServiceMain` .

> [!NOTE]
> Niepowodzenie `StartServiceCtrlDispatcher` połączenia z menedżerem sterowania usługami (SCM) prawdopodobnie oznacza, że program nie jest uruchomiony jako usługa. W takim przypadku program wywołuje się `CAtlServiceModuleT::Run` bezpośrednio, aby program mógł zostać uruchomiony jako serwer lokalny. Aby uzyskać więcej informacji na temat uruchamiania programu jako serwera lokalnego, zobacz [porady dotyczące debugowania](../atl/debugging-tips.md).

## <a name="see-also"></a>Zobacz też

[Usługi](../atl/atl-services.md)<br/>
[Funkcja CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#start)
