---
description: 'Dowiedz się więcej o programie: Uruchamianie programu jako serwera lokalnego'
title: Uruchamianie programu jako serwera lokalnego
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: 1cdf3cef0773769318d68964b28bb60ca66666d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157494"
---
# <a name="running-the-program-as-a-local-server"></a>Uruchamianie programu jako serwera lokalnego

Jeśli Uruchamianie programu jako usługi jest niewygodne, można tymczasowo zmienić rejestr, aby program był uruchamiany jako normalny serwer lokalny. Wystarczy zmienić nazwę `LocalService` wartości w identyfikatorze AppID na `_LocalService` i upewnić się, że `LocalServer32` klucz w obszarze CLSID został poprawnie ustawiony. (Należy pamiętać, że przy użyciu programu DCOMCNFG, aby określić, że aplikacja powinna być uruchamiana na innym komputerze, zmienia nazwę `LocalServer32` klucza na `_LocalServer32` ). Uruchomienie programu jako serwera lokalnego zajmuje kilka sekund podczas uruchamiania, ponieważ wywołanie `StartServiceCtrlDispatcher` w `CAtlServiceModuleT::Start` ciągu kilku sekund przed zakończeniem się niepowodzeniem.

## <a name="see-also"></a>Zobacz też

[Porady dotyczące debugowania](../atl/debugging-tips.md)
