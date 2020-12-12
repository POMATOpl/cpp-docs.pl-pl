---
description: 'Dowiedz się więcej o: Funkcja CAtlServiceModuleT:: ServiceMain — funkcja'
title: 'Funkcja CAtlServiceModuleT:: ServiceMain — funkcja'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 97093d13a2f13ea0d6bd4ba5db46bef45d239cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148333"
---
# <a name="catlservicemoduletservicemain-function"></a>Funkcja CAtlServiceModuleT:: ServiceMain — funkcja

Wywołania Menedżera sterowania usługami (SCM) `ServiceMain` po otwarciu aplikacji panelu sterowania wybierz usługę, a następnie kliknij przycisk **Uruchom**.

Po wywołaniach SCM `ServiceMain` Usługa musi udzielić funkcji programu obsługi SCM. Ta funkcja umożliwia menedżerowi SCM uzyskanie stanu usługi i przekazywanie określonych instrukcji (takich jak Wstrzymywanie lub zatrzymywanie). Menedżer SCM otrzymuje tę funkcję, gdy usługa przejdzie `_Handler` do funkcji Win32 API, [RegisterServiceCtrlHandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw). ( `_Handler` to statyczna funkcja członkowska, która wywołuje [procedurę obsługi](../atl/reference/catlservicemodulet-class.md#handler)niestatycznej funkcji członkowskiej).

Podczas uruchamiania usługa powinna również poinformować menedżer SCM o jego bieżącym stanie. Robi to przez przekazanie SERVICE_START_PENDING do funkcji Win32 API, [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus).

`ServiceMain` następnie wywołuje metodę `CAtlExeModuleT::InitializeCom` , która wywołuje funkcję Win32 API [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex). Domyślnie `InitializeCom` przekazuje flagę COINIT_MULTITHREADED do funkcji. Ta flaga wskazuje, że program ma być serwerem wolnych wątków.

Teraz `CAtlServiceModuleT::Run` jest wywoływana w celu wykonania głównej pracy usługi. `Run` kontynuuje wykonywanie, dopóki usługa nie zostanie zatrzymana.

## <a name="see-also"></a>Zobacz też

[Usługi](../atl/atl-services.md)<br/>
[Funkcja CAtlServiceModuleT:: ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
