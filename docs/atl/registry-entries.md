---
description: 'Dowiedz się więcej na temat: wpisy rejestru'
title: Wpisy rejestru (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: c89c8f64a91c09f16333c3381a33d792332543d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138583"
---
# <a name="registry-entries"></a>Wpisy rejestru

Model DCOM wprowadził koncepcję identyfikatorów aplikacji (AppID), które grupują opcje konfiguracji dla co najmniej jednego obiektu DCOM w scentralizowaną lokalizację w rejestrze. Identyfikator AppID można określić, wskazując jego wartość w identyfikatorze CLSID o nazwie.

Domyślnie usługa wygenerowana przez ATL używa swojego identyfikatora CLSID jako identyfikatora GUID dla jego AppID. W obszarze `HKEY_CLASSES_ROOT\AppID` można określić wpisy specyficzne dla modelu DCOM. Początkowo istnieją dwa wpisy:

- `LocalService`, o wartości równej nazwie usługi. Jeśli ta wartość istnieje, jest używana zamiast `LocalServer32` klucza pod identyfikatorem CLSID.

- `ServiceParameters`, o wartości równej `-Service` . Ta wartość określa parametry, które zostaną przesłane do usługi po jej uruchomieniu. Należy zauważyć, że te parametry są przesyłane do `ServiceMain` funkcji usługi, a nie `WinMain` .

Wszystkie usługi DCOM muszą również utworzyć inny klucz w obszarze `HKEY_CLASSES_ROOT\AppID` . Ten klucz jest równy nazwie pliku EXE i działa jako odwołanie krzyżowe, ponieważ zawiera wartość identyfikatora AppID wskazującą z powrotem do wpisów AppID.

## <a name="see-also"></a>Zobacz też

[Usługi](../atl/atl-services.md)
