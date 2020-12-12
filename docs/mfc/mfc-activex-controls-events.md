---
description: 'Dowiedz się więcej o: kontrolki ActiveX MFC: zdarzenia'
title: 'Formanty MFC ActiveX: zdarzenia'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
ms.openlocfilehash: 8a360931287432e9f0ee0fc55e7e5120bcbd390f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240692"
---
# <a name="mfc-activex-controls-events"></a>Formanty MFC ActiveX: zdarzenia

Kontrolki ActiveX używają zdarzeń do powiadamiania kontenera, że coś się stało z kontrolką. Typowe przykłady zdarzeń obejmują kliknięcia kontrolki, dane wprowadzone przy użyciu klawiatury oraz zmiany stanu formantu. Gdy te akcje wystąpią, formant uruchamia zdarzenie, aby ostrzec kontener.

Zdarzenia są również nazywane komunikatami.

MFC obsługuje dwa rodzaje zdarzeń: giełdowe i niestandardowe. Zdarzenia giełdowe to zdarzenia, które Klasa [COleControl](reference/colecontrol-class.md) obsługuje automatycznie. Aby uzyskać pełną listę zdarzeń giełdowych, zobacz artykuł [kontrolki ActiveX MFC: Dodawanie zdarzeń giełdowych](mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Zdarzenia niestandardowe umożliwiają kontrolce powiadomienie kontenera o wystąpieniu akcji specyficznej dla tej kontrolki. Niektóre przykłady to zmiana stanu wewnętrznego kontrolki lub otrzymania określonego komunikatu w oknie.

Aby formant uruchamiał zdarzenia prawidłowo, Klasa formantów musi mapować każde zdarzenie formantu do funkcji członkowskiej, która powinna być wywoływana w przypadku wystąpienia zdarzenia powiązanego. Ten mechanizm mapowania (nazywany mapą zdarzeń) służy do scentralizowania informacji o zdarzeniu i umożliwia programowi Visual Studio łatwe uzyskiwanie dostępu do zdarzeń kontrolki i manipulowanie nimi. Ta mapa zdarzeń jest zadeklarowana przez następujące makro znajdujące się w nagłówku (. H) plik deklaracji klasy kontroli:

[!code-cpp[NVC_MFC_AxUI#2](codesnippet/cpp/mfc-activex-controls-events_1.h)]

Po zadeklarowaniu mapy zdarzeń musi ona być zdefiniowana w implementacji kontrolki (. CPP). Następujące wiersze kodu definiują mapę zdarzeń, umożliwiając formantowi uruchomienie określonych zdarzeń:

[!code-cpp[NVC_MFC_AxUI#3](codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

W przypadku utworzenia projektu przy użyciu kreatora kontrolek ActiveX MFC program automatycznie dodaje te wiersze. Jeśli nie używasz Kreatora kontrolek ActiveX MFC, musisz dodać te wiersze ręcznie.

Za pomocą Widok klasy można dodawać zdarzenia giełdowe obsługiwane przez `COleControl` zdefiniowane przez siebie zdarzenia dotyczące klasy lub niestandardowych. Dla każdego nowego zdarzenia Widok klasy automatycznie dodaje właściwy wpis do mapy zdarzeń kontrolki i kontrolki. Plik IDL.

W dwóch innych artykułach szczegółowo omówiono zdarzenia:

- [Kontrolki ActiveX MFC: Dodawanie zdarzeń giełdowych](mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Kontrolki ActiveX MFC: Dodawanie zdarzeń niestandardowych](mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC](mfc-activex-controls.md)<br/>
[Kontrolki ActiveX MFC: metody](mfc-activex-controls-methods.md)<br/>
[Klasa COleControl](reference/colecontrol-class.md)
