---
description: 'Dowiedz się więcej o programie: usługi ATL'
title: Usługi ATL
ms.date: 11/04/2016
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 1cb1f526434cefe57dc4675d592f836e04a6cdb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148606"
---
# <a name="atl-services"></a>Usługi ATL

Aby utworzyć obiekt ATL COM w taki sposób, aby był uruchamiany w usłudze, po prostu wybierz pozycję Usługa (EXE) z listy opcji serwera w Kreatorze projektu ATL. Następnie Kreator utworzy klasę pochodną w `CAtlServiceModuleT` celu zaimplementowania usługi.

Gdy obiekt ATL COM jest zbudowany jako usługa, zostanie on zarejestrowany tylko jako serwer lokalny i nie będzie wyświetlany na liście usług w panelu sterowania. Jest to spowodowane tym, że łatwiej jest debugować usługę jako serwer lokalny, a nie jako usługa. Aby zainstalować ją jako usługę, uruchom następujące polecenie w wierszu polecenia:

`YourEXE` `.exe /Service`

Aby go odinstalować, uruchom następujące polecenie:

`YourEXE` `.exe /UnregServer`

W pierwszych czterech tematach w tej sekcji omówiono akcje, które występują podczas wykonywania `CAtlServiceModuleT` funkcji Członkowskich. Te tematy są wyświetlane w tej samej kolejności, w jakiej są zwykle wywoływane. Aby ulepszyć zrozumienie tych tematów, dobrym pomysłem jest użycie kodu źródłowego wygenerowanego przez Kreatora projektu ATL jako odwołania. Cztery pierwsze tematy to:

- [Funkcja CAtlServiceModuleT:: Start — funkcja](../atl/reference/catlservicemodulet-class.md#start)

- [Funkcja CAtlServiceModuleT:: ServiceMain — funkcja](../atl/reference/catlservicemodulet-class.md#servicemain)

- [Funkcja CAtlServiceModuleT:: Run — funkcja](../atl/reference/catlservicemodulet-class.md#run)

- [Funkcja CAtlServiceModuleT:: Handler — funkcja](../atl/reference/catlservicemodulet-class.md#handler)

W ostatnich trzech tematach omówiono koncepcje związane z tworzeniem usługi:

- [Wpisy rejestru](../atl/registry-entries.md) dla usług ATL

- [DCOMCNFG](../atl/dcomcnfg.md)

- [Porady dotyczące debugowania](../atl/debugging-tips.md) usług ATL

## <a name="see-also"></a>Zobacz też

[Pojęcia](../atl/active-template-library-atl-concepts.md)
