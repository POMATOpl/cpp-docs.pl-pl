---
description: 'Dowiedz się więcej na temat: Funkcja CAtlServiceModuleT:: Run — funkcja'
title: 'Funkcja CAtlServiceModuleT:: Run — funkcja'
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: f8bba170236138f6491c49506bccd29bc23d9dec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148346"
---
# <a name="catlservicemoduletrun-function"></a>Funkcja CAtlServiceModuleT:: Run — funkcja

`Run` zawiera wywołania do `PreMessageLoop` , `RunMessageLoop` , i `PostMessageLoop` . Po wywołaniu należy `PreMessageLoop` najpierw przechowywać identyfikator wątku usługi. Usługa będzie używać tego identyfikatora do zamykania, wysyłając wiadomość WM_QUIT przy użyciu funkcji Win32 API, [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew).

`PreMessageLoop` następnie wywołuje `InitializeSecurity` . Domyślnie program `InitializeSecurity` wywołuje [CoInitializeSecurity](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) z deskryptorem zabezpieczeń ustawionym na wartość null, co oznacza, że każdy użytkownik ma dostęp do obiektu.

Jeśli nie chcesz, aby usługa określiła własne zabezpieczenia, przesłonięcia `PreMessageLoop` i nie Wywołaj `InitializeSecurity` , a następnie com określi ustawienia zabezpieczeń z rejestru. Wygodnym sposobem konfigurowania ustawień rejestru jest narzędzie [DCOMCNFG](../atl/dcomcnfg.md) opisane w dalszej części tej sekcji.

Po określeniu zabezpieczeń obiekt jest zarejestrowany w modelu COM, dzięki czemu nowi klienci mogą łączyć się z programem. Na koniec program instruuje menedżera kontroli usług (SCM), że jest uruchomiony, a program wprowadza pętlę komunikatów. Program pozostaje uruchomiony do momentu opublikowania komunikatu zamknięcia po zamknięciu usługi.

## <a name="see-also"></a>Zobacz też

[Usługi](../atl/atl-services.md)<br/>
[Klasa CSecurityDesc](../atl/reference/csecuritydesc-class.md)<br/>
[CSid, Klasa](../atl/reference/csid-class.md)<br/>
[Klasa CDacl](../atl/reference/cdacl-class.md)<br/>
[Funkcja CAtlServiceModuleT:: Run](../atl/reference/catlservicemodulet-class.md#run)
