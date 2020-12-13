---
description: 'Dowiedz się więcej na temat: co robią okna ramowe'
title: Co robią okna ramowe
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: 8f70bbe55b15310133688079236fe57459679090
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142834"
---
# <a name="what-frame-windows-do"></a>Co robią okna ramowe

Oprócz prostej ramki widoku okna ramowe są odpowiedzialne za wiele zadań związanych z koordynowaniem ramki z widokiem i aplikacją. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) i [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) dziedziczą z [obiektu CFrameWnd](../mfc/reference/cframewnd-class.md), dzięki czemu mają `CFrameWnd` możliwości, a także nowe możliwości, które dodają. Przykłady podrzędnych okien dialogowych, kontrolki, takie jak przyciski i pola list oraz paski sterowania, w tym paski narzędzi, paski stanu i paski okien dialogowych.

Okno ramy jest odpowiedzialne za zarządzanie układem jego okien podrzędnych. W strukturze MFC okno ramki umieszcza dowolne paski kontroli, widoki i inne okna podrzędne wewnątrz jego obszaru klienckiego.

Okno ramki również przekazuje polecenia do swoich widoków i może odpowiadać na komunikaty powiadomień z okien kontroli.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Paski sterowania (jak mieszczą się w oknie ramki)](../mfc/control-bars.md)

- [Zarządzanie menu, paskami sterowania i akceleratorami (jak mieszczą się w oknie ramki)](../mfc/managing-menus-control-bars-and-accelerators.md)

- [Routing poleceń (z okna ramowego do jego widoku i innych elementów docelowych poleceń)](../mfc/command-routing.md)

- [Architektura dokumentu/View](../mfc/document-view-architecture.md)

- [Paski sterowania](../mfc/control-bars.md)

- [Formanty](../mfc/controls-mfc.md)

## <a name="see-also"></a>Zobacz też

[Okna ramowe](../mfc/frame-windows.md)
