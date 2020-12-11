---
description: 'Dowiedz się więcej o programie: mapy komunikatów (ATL)'
title: Mapy komunikatów (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: c5b3340abbfbc66ac710ab716e3daa38dd7cd6df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159521"
---
# <a name="message-maps-atl"></a>Mapy komunikatów (ATL)

Mapa komunikatów kojarzy funkcję procedury obsługi z konkretnym komunikatem, poleceniem lub powiadomieniem. Korzystając z [makr mapy komunikatów](../atl/reference/message-map-macros-atl.md)ATL, można określić mapę komunikatów dla okna. Okna procedury w `CWindowImpl` , `CDialogImpl` i `CContainedWindowT` kierują komunikaty okna do mapy komunikatów.

[Funkcje obsługi komunikatów](../atl/message-handler-functions.md) akceptują dodatkowy argument typu `BOOL&` . Ten argument wskazuje, czy komunikat został przetworzony i domyślnie ma ustawioną wartość TRUE. Funkcja obsługi może następnie ustawić dla argumentu wartość FALSE, aby wskazać, że komunikat nie został obsłużony. W takim przypadku ATL będzie nadal szukać funkcji obsługi w mapie wiadomości. Ustawiając dla tego argumentu wartość FALSE, można najpierw wykonać pewne działania w odpowiedzi na komunikat, a następnie zezwolić na przetwarzanie domyślne lub inną funkcję obsługi, aby zakończyć obsługę wiadomości.

## <a name="chained-message-maps"></a>Mapy komunikatów łańcucha

ATL umożliwia również łączenie map komunikatów, które kierują obsługę komunikatów do mapy komunikatów zdefiniowanej w innej klasie. Na przykład, można zaimplementować wspólną obsługę komunikatów w oddzielnym klasie, aby zapewnić ujednolicone zachowanie wszystkich łańcuchów systemu Windows do tej klasy. Można łączyć łańcuch z klasą bazową lub elementem członkowskim danych klasy.

ATL obsługuje również dynamiczne łączenie, które umożliwia łańcuchowanie do mapy komunikatów innego obiektu w czasie wykonywania. Aby zaimplementować dynamiczne łączenie, należy utworzyć klasę z [CDynamicChain](../atl/reference/cdynamicchain-class.md). Następnie zadeklaruj makro [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) w mapie wiadomości. CHAIN_MSG_MAP_DYNAMIC wymaga unikatowego numeru, który identyfikuje obiekt i mapę komunikatów, do której tworzysz łańcuch. Należy zdefiniować tę unikatową wartość za pomocą wywołania do `CDynamicChain::SetChainEntry` .

Można utworzyć łańcuch do dowolnej klasy, która deklaruje mapę komunikatów, pod warunkiem, że Klasa pochodzi od [CMessageMap](../atl/reference/cmessagemap-class.md). `CMessageMap` umożliwia obiektowi uwidocznienie map komunikatów na innych obiektach. Należy zauważyć, że `CWindowImpl` już pochodzi od `CMessageMap` .

## <a name="alternate-message-maps"></a>Alternatywne mapowania komunikatów

Na koniec ATL obsługuje alternatywne mapy komunikatów zadeklarowane za pomocą makra [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) . Każda alternatywna Mapa komunikatów jest identyfikowana przez unikatowy numer, który jest przekazywany do ALT_MSG_MAP. Korzystając z alternatywnych map komunikatów, można obsługiwać komunikaty wielu okien w jednej mapie. Należy pamiętać, że domyślnie program nie `CWindowImpl` używa alternatywnych map komunikatów. Aby dodać tę obsługę, Zastąp `WindowProc` metodę w `CWindowImpl` klasie pochodnej i Wywołaj `ProcessWindowMessage` z identyfikatorem mapy komunikatów.

## <a name="see-also"></a>Zobacz też

[Implementowanie okna](../atl/implementing-a-window.md)
