---
description: 'Dowiedz się więcej o programie: punkty połączenia ATL'
title: Punkty połączenia ATL
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 60b9018185bea2af26407ee9d7a203148c8dc477
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165826"
---
# <a name="atl-connection-points"></a>Punkty połączenia ATL

Obiekt, który ma być połączony, obsługuje interfejsy wychodzące. Interfejs wychodzący umożliwia obiektowi komunikowanie się z klientem. Dla każdego interfejsu wychodzącego obiekt łączący uwidacznia punkt połączenia. Każdy interfejs wychodzący jest implementowany przez klienta na obiekcie o nazwie ujścia.

![Punkty połączenia](../atl/media/vc2zw31.gif "Punkty połączenia")

Każdy punkt połączenia obsługuje interfejs [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) . Obiekt, który można połączyć, udostępnia swoje punkty połączenia klientowi za pomocą interfejsu [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer) .

## <a name="in-this-section"></a>W tej sekcji

[Klasy punktów połączenia ATL](../atl/atl-connection-point-classes.md)<br/>
Zwięźle opisuje klasy ATL, które obsługują punkty połączenia.

[Dodawanie punktów połączenia do obiektu](../atl/adding-connection-points-to-an-object.md)<br/>
Przedstawia kroki służące do dodawania punktów połączenia do obiektu.

[Przykład punktu połączenia ATL](../atl/atl-connection-point-example.md)<br/>
Zawiera przykład deklarowania punktu połączenia.

## <a name="related-sections"></a>Sekcje pokrewne

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Zawiera łącza do tematów koncepcyjnych dotyczących sposobu programowania przy użyciu Active Template Library.

## <a name="see-also"></a>Zobacz też

[Pojęcia](../atl/active-template-library-atl-concepts.md)
