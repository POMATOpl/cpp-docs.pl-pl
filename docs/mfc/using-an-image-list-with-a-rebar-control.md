---
description: 'Dowiedz się więcej o programie: używanie listy obrazów z kontrolką paska pomocniczego'
title: Używanie listy obrazów z formantem paska pomocniczego
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
ms.openlocfilehash: ae4aa0259cbe850dbab8ef4bc04277014b39e357
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271801"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Używanie listy obrazów z formantem paska pomocniczego

Każda grupa paska pomocniczego może zawierać, między innymi, obraz ze skojarzonej listy obrazów. Poniższa procedura zawiera szczegółowe instrukcje dotyczące wyświetlania obrazu w paśmie paska pomocniczego.

### <a name="to-display-images-in-a-rebar-band"></a>Aby wyświetlić obrazy w paśmie paska pomocniczego

1. Dołącz listę obrazów do obiektu formantu paska pomocniczego, wykonując wywołanie metody [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), przekazując wskaźnik do istniejącej listy obrazów.

1. Zmodyfikuj strukturę **REBARBANDINFO** , aby przypisać obraz do pasma paska pomocniczego:

   - Ustaw element członkowski *fmask* na `RBBIM_IMAGE` , używając operatora bitowego or, aby uwzględnić dodatkowe flagi w razie potrzeby.

   - Ustaw element członkowski *IImage* na indeks listy obrazów obrazu, który ma być wyświetlany.

1. Zainicjuj wszystkie pozostałe elementy członkowskie danych, takie jak rozmiar, tekst i uchwyt okna zawartego podrzędnego, z wymaganymi informacjami.

1. Wstaw nowy pasek (z obrazem) z wywołaniem do [Korzystanie CReBarCtrl:: InsertBand](../mfc/reference/crebarctrl-class.md#insertband), przekazując strukturę **REBARBANDINFO** .

W poniższym przykładzie przyjęto założenie, że istniejący obiekt listy obrazów z dwoma obrazami został dołączony do obiektu sterowania paska pomocniczego ( `m_wndReBar` ). Nowy pasek paska pomocniczego (zdefiniowany przez `rbi` ), zawierający pierwszy obraz, jest dodawany z wywołaniem do `InsertBand` :

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>Zobacz też

[Korzystanie z CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
