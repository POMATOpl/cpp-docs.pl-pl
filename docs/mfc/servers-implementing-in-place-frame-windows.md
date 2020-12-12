---
description: 'Dowiedz się więcej o programie: serwery: implementowanie okien ramowych In-Place'
title: 'Serwery: implementowanie okien ramowych w miejscu'
ms.date: 09/09/2019
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
ms.openlocfilehash: 859a31bf107162aea6adb4d40ccf7b7b87f485b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217357"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Serwery: implementowanie okien ramowych w miejscu

W tym artykule wyjaśniono, co należy zrobić, aby zaimplementować okna ramek w miejscu w aplikacji serwera do edycji wizualnej, jeśli nie używasz Kreatora aplikacji do utworzenia aplikacji serwera. Zamiast poniższej procedury opisanej w tym artykule można użyć istniejącej klasy okien ramowych w miejscu z aplikacji wygenerowanej przez Kreatora aplikacji lub przykładu dostarczonego z Visual C++.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Aby zadeklarować klasę okien ramowych w miejscu

1. Utwórz klasę okien ramowych w miejscu z `COleIPFrameWnd` .

   - Użyj makra DECLARE_DYNCREATE w pliku nagłówkowym klasy.

   - Użyj makra IMPLEMENT_DYNCREATE w pliku implementacji klasy (. cpp). Pozwala to na utworzenie obiektów tej klasy przez strukturę.

1. Zadeklaruj `COleResizeBar` element członkowski w klasie okien ramowych. Jest to konieczne, jeśli chcesz obsługiwać zmiany w miejscu w aplikacjach serwerowych.

   Zadeklaruj `OnCreate` procedurę obsługi komunikatów (za pomocą [kreatora klas](reference/mfc-class-wizard.md)) i Wywołaj `Create` dla `COleResizeBar` elementu członkowskiego, jeśli został on zdefiniowany.

1. Jeśli masz pasek narzędzi, zadeklaruj `CToolBar` element członkowski w klasie okien ramowych.

   Przesłoń `OnCreateControlBars` funkcję członkowską, aby utworzyć pasek narzędzi, gdy serwer jest aktywny. Na przykład:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   Zapoznaj się z omówieniem tego kodu w kroku 5.

1. Dołącz plik nagłówka dla tej klasy okna ramowego w miejscu w głównym pliku CPP.

1. W `InitInstance` przypadku klasy aplikacji Wywołaj `SetServerInfo` funkcję obiektu szablonu dokumentu, aby określić zasoby i okno ramki w miejscu do użycia w edycji otwartych i w miejscu.

Seria wywołań funkcji w **`if`** instrukcji tworzy pasek narzędzi z zasobów udostępnianych przez serwer. W tym momencie pasek narzędzi jest częścią hierarchii okna kontenera. Ponieważ ten pasek narzędzi pochodzi od `CToolBar` , przekaże jego komunikaty do jego właściciela, okna ramki aplikacji kontenera, chyba że zmienisz właściciela. To dlatego, że wywołanie `SetOwner` jest wymagane. To wywołanie zmienia okno, w którym polecenia są wysyłane, aby były oknem ramki w miejscu serwera, co powoduje, że komunikaty są przekazywane do serwera. Dzięki temu serwer może reagować na operacje na pasku narzędzi, który zapewnia.

Identyfikator mapy bitowej paska narzędzi powinien być taki sam jak w przypadku innych zasobów w miejscu zdefiniowanych w aplikacji serwera. Zobacz [menu i zasoby: Dodatki do serwera,](../mfc/menus-and-resources-server-additions.md) Aby uzyskać szczegółowe informacje.

Aby uzyskać więcej informacji, zobacz [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md)i [CDocTemplate:: SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) w *dokumentacji biblioteki klas*.

## <a name="see-also"></a>Zobacz też

[Serwery](../mfc/servers.md)<br/>
[Serwery: implementowanie serwera](../mfc/servers-implementing-a-server.md)<br/>
[Serwery: implementowanie dokumentów serwera](../mfc/servers-implementing-server-documents.md)<br/>
[Serwery: elementy serwera](../mfc/servers-server-items.md)
