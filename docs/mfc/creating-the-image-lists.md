---
description: 'Dowiedz się więcej o programie: Tworzenie list obrazów'
title: Tworzenie list obrazów
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: f2776902e7be06161bdbcfad23bd21d9188467f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309670"
---
# <a name="creating-the-image-lists"></a>Tworzenie list obrazów

Tworzenie list obrazów jest takie samo, jak w przypadku używania [CListView](reference/clistview-class.md) lub [CListCtrl](reference/clistctrl-class.md).

> [!NOTE]
> Tylko listy obrazów są potrzebne, Jeśli kontrolka listy zawiera `LVS_ICON` styl.

Użyj klasy `CImageList` , aby utworzyć co najmniej jedną listę obrazów (dla ikon o pełnym rozmiarze, małych ikon i Stanów). Zobacz [Korzystanie CImageList](reference/cimagelist-class.md)i zobacz [listę obrazów widoku listy](/windows/win32/Controls/using-list-view-controls) w Windows SDK.

Wywołaj [CListCtrl:: SetImageList](reference/clistctrl-class.md#setimagelist) dla każdej listy obrazów; Przekaż wskaźnik do odpowiedniego `CImageList` obiektu.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CListCtrl](using-clistctrl.md)<br/>
[Formanty](controls-mfc.md)
