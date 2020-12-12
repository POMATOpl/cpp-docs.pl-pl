---
description: 'Dowiedz się więcej na temat: używanie paska dialogowego z kontrolką paska pomocniczego'
title: Używanie paska dialogowego z formantem paska pomocniczego
ms.date: 11/04/2016
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
ms.openlocfilehash: 97fb8ca5c356d91fa4b4ba44753fbdc9bf298435
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263533"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Używanie paska dialogowego z formantem paska pomocniczego

Jak wspomniano w [kontrolkach paska pomocniczego i grupach](../mfc/rebar-controls-and-bands.md), każda grupa może zawierać tylko jedno okno podrzędne (lub kontrolkę). Może to być ograniczenie, jeśli chcesz mieć więcej niż jedno okno podrzędne na pasmo. Wygodnym obejściem jest utworzenie zasobu paska dialogowego z wieloma kontrolkami, a następnie dodanie pasma paska pomocniczego (zawierającego pasek dialogowe) do kontrolki paska pomocniczego.

Normalnie, jeśli chcesz, aby pasek okna dialogowego był widoczny jako przezroczysty, ustaw WS_EX_TRANSPARENT styl rozszerzony dla obiektu paska narzędzi. Ponieważ jednak w WS_EX_TRANSPARENT wystąpiły pewne problemy związane z prawidłowym rysowaniem tła paska dialogowego, należy wykonać trochę dodatkowej pracy, aby osiągnąć żądany efekt.

Poniższa procedura zawiera szczegółowe instrukcje niezbędne do osiągnięcia przejrzystości bez użycia stylu rozszerzonego WS_EX_TRANSPARENT.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Aby zaimplementować przezroczysty pasek okna dialogowego w paśmie paska pomocniczego

1. Za pomocą [okna dialogowego Dodaj klasę](../mfc/reference/adding-an-mfc-class.md)Dodaj nową klasę (na przykład `CMyDlgBar` ) implementującą obiekt paska dialogowego.

1. Dodaj procedurę obsługi dla komunikatu WM_ERASEBKGND.

1. W nowej obsłudze zmodyfikuj istniejący kod, aby dopasować go do poniższego przykładu:

   [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. Dodaj procedurę obsługi dla komunikatu WM_MOVE.

1. W nowej obsłudze zmodyfikuj istniejący kod, aby dopasować go do poniższego przykładu:

   [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Nowe programy obsługi symulują przezroczystość paska dialogowego przez przekazanie komunikatu WM_ERASEBKGND do okna nadrzędnego i wymuszenie odświeżenia za każdym razem, gdy obiekt paska okna dialogowego zostanie przeniesiony.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
