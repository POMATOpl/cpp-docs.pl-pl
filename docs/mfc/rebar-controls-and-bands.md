---
description: 'Dowiedz się więcej na temat: kontrolki paska pomocniczego i paski'
title: Formanty paska pomocniczego i paski
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
ms.openlocfilehash: 27ada3633a560ad8b5852b05bdd6330a0936fb99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248570"
---
# <a name="rebar-controls-and-bands"></a>Formanty paska pomocniczego i paski

Głównym celem formantu paska pomocniczego jest działanie jako kontener dla okien podrzędnych, wspólnych kontrolek dialogowych, menu, pasków narzędzi itd. To zawieranie jest obsługiwane przez koncepcję "pasma". Każda grupa paska pomocniczego może zawierać dowolną kombinację paska uchwytu, mapy bitowej, etykiety tekstowej i okna podrzędnego.

Klasa `CReBarCtrl` ma wiele funkcji Członkowskich, których można użyć do pobierania i manipulowania informacjami dla określonego pasma paska pomocniczego:

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) Pobiera liczbę bieżących pasków w kontrolce paska pomocniczego.

- [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) Inicjuje strukturę **REBARBANDINFO** z informacjami z określonego pasma. Istnieje odpowiednia funkcja członkowska [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) .

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) Pobiera prostokąt związany z określonym pasmem.

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) Pobiera liczbę wierszy pasma w kontrolce paska pomocniczego.

- [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) Pobiera indeks określonego pasma.

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) Pobiera obramowania pasma.

Oprócz manipulowania dostępne są różne funkcje członkowskie, które umożliwiają działanie na określonych paska pomocniczego pasm.

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) i [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) Dodaj i Usuń przedziały paska pomocniczego. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) i [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) wpływają na bieżący rozmiar konkretnego pasma paska pomocniczego. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) zmienia indeks określonego pasma paska pomocniczego. [Showband](../mfc/reference/crebarctrl-class.md#showband) pokazuje lub ukrywa pasmo paska pomocniczego z użytkownika.

Poniższy przykład ilustruje Dodawanie paska narzędzi (*m_wndToolBar*) do istniejącej kontrolki paska pomocniczego (*m_wndReBar*). Pasmo opisano przez zainicjowanie `rbi` struktury, a następnie wywołanie `InsertBand` funkcji składowej:

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>Zobacz też

[Korzystanie z CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
