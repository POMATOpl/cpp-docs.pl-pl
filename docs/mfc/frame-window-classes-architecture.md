---
description: 'Dowiedz się więcej na temat: klasy okien ramowych (architektura)'
title: Klasy okien ramowych (architektura)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 045108cd1e45325cf6069b5d8259ffab9abb0c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155036"
---
# <a name="frame-window-classes-architecture"></a>Klasy okien ramowych (architektura)

W obszarze architektura dokumentu/widoku okna z ramkami są okna zawierające okno wyświetlania. Obsługują one również paski kontroli dołączone do nich.

W aplikacjach interfejsu wielu dokumentów (MDI) główne okno pochodzi od `CMDIFrameWnd` . Zawiera on pośrednio ramki dokumentów, które są `CMDIChildWnd` obiektami. `CMDIChildWnd`Obiekty z kolei zawierają widoki dokumentów.

W aplikacjach interfejsu pojedynczego dokumentu (SDI) główne okno pochodne od `CFrameWnd` , zawiera widok bieżącego dokumentu.

[CFrameWnd](reference/cframewnd-class.md)<br/>
Klasa bazowa dla głównego okna ramki aplikacji SDI. Również Klasa bazowa dla wszystkich innych klas okien ramowych.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
Klasa bazowa dla głównego okna ramki aplikacji MDI.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
Klasa bazowa dla okien ramowych dokumentu aplikacji MDI.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Udostępnia okno ramek dla widoku, gdy dokument serwera jest edytowany w miejscu.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
