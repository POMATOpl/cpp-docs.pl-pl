---
description: 'Dowiedz się więcej na temat: Tworzenie formantu paska pomocniczego'
title: Tworzenie formantu paska pomocniczego
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 71328af9d4701c412f7876629ebd2a56fa8ffd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310021"
---
# <a name="creating-a-rebar-control"></a>Tworzenie formantu paska pomocniczego

Obiekty [Korzystanie CReBarCtrl](reference/crebarctrl-class.md) należy utworzyć przed wyświetleniem obiektu nadrzędnego. Pozwala to zminimalizować możliwości rysowania.

Na przykład formanty paska pomocniczego (używane w obiektach okien ramowych) są często używane jako okna nadrzędne dla formantów paska narzędzi. W związku z tym element nadrzędny formantu paska pomocniczego jest obiektem okna ramowego. Ponieważ obiekt okna ramki jest elementem nadrzędnym, `OnCreate` funkcja członkowska (obiektu nadrzędnego) jest doskonałym miejscem do utworzenia formantu paska pomocniczego.

Aby użyć `CReBarCtrl` obiektu, zwykle wykonaj następujące kroki:

### <a name="to-use-a-crebarctrl-object"></a>Aby użyć obiektu korzystanie CReBarCtrl

1. Utwórz obiekt [Korzystanie CReBarCtrl](reference/crebarctrl-class.md) .

1. Wywołanie [Create](reference/crebarctrl-class.md#create) w celu utworzenia formantu paska pomocniczego systemu Windows i dołączenia go do `CReBarCtrl` obiektu, określając wszystkie wymagane style.

1. Załaduj mapę bitową z wywołaniem do [CBitmap:: LoadBitmap](reference/cbitmap-class.md#loadbitmap), która ma być używana jako tło obiektu formantu paska pomocniczego.

1. Utwórz i zainicjuj wszystkie podrzędne obiekty okna (paski narzędzi, kontrolki okna dialogowego itd.), które będą zawarte w obiekcie sterowania paska pomocniczego.

1. Zainicjuj strukturę **REBARBANDINFO** z niezbędnymi informacjami dla przedziału, który ma zostać wstawiony.

1. Wywołaj [InsertBand](reference/crebarctrl-class.md#insertband) , aby wstawić istniejące okna podrzędne (na przykład `m_wndReToolBar` ) do nowej kontrolki paska pomocniczego. Aby uzyskać więcej informacji na temat wstawiania pasm do istniejącej kontrolki paska pomocniczego, zobacz [paska pomocniczego Controls and banderoles](rebar-controls-and-bands.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CReBarCtrl](using-crebarctrl.md)<br/>
[Formanty](controls-mfc.md)
