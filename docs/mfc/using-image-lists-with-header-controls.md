---
description: 'Dowiedz się więcej o programie: Używanie list obrazów z kontrolkami nagłówka'
title: Używanie list obrazów z formantami nagłówka
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 549f54c9fae7e0e0a63c726f4b75d2adeb38eef8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322734"
---
# <a name="using-image-lists-with-header-controls"></a>Używanie list obrazów z formantami nagłówka

Elementy nagłówka mają możliwość wyświetlania obrazu w elemencie nagłówka. Ten obraz przechowywany na liście skojarzonych obrazów ma 16 x 16 pikseli i ma takie same charakterystyki, jak obrazy ikon używane w kontrolce widoku listy. W celu pomyślnego wdrożenia tego zachowania należy najpierw utworzyć i zainicjować listę obrazów, skojarzyć listę z kontrolką nagłówka, a następnie zmodyfikować atrybuty elementu nagłówka, który będzie wyświetlał obraz.

Poniższa procedura ilustruje szczegóły przy użyciu wskaźnika do kontrolki nagłówka ( `m_pHdrCtrl` ) i wskaźnika do listy obrazów ( `m_pHdrImages` ).

### <a name="to-display-an-image-in-a-header-item"></a>Aby wyświetlić obraz w elemencie nagłówka

1. Utwórz nową listę obrazów (lub Użyj istniejącego obiektu listy obrazów) przy użyciu konstruktora [Korzystanie CImageList](../mfc/reference/cimagelist-class.md) , przechowując wynikowy wskaźnik.

1. Zainicjuj nowy obiekt listy obrazów przez wywołanie [Korzystanie CImageList:: Create](../mfc/reference/cimagelist-class.md#create). Poniższy kod jest przykładem tego wywołania.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. Dodaj obrazy dla każdego elementu nagłówka. Poniższy kod dodaje dwa wstępnie zdefiniowane obrazy.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. Skojarz listę obrazów z kontrolką nagłówka z wywołaniem do [CHeaderCtrl:: SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist).

1. Zmodyfikuj element nagłówka, aby wyświetlić obraz z listy skojarzonych obrazów. Poniższy przykład przypisuje pierwszy obraz z `m_phdrImages` , do pierwszego elementu nagłówka, `m_pHdrCtrl` .

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

Aby uzyskać szczegółowe informacje na temat używanych wartości parametrów, zapoznaj się z odpowiednimi [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).

> [!NOTE]
> Istnieje możliwość, że istnieje wiele kontrolek z tą samą listą obrazów. Na przykład w standardowej kontrolce widok listy może istnieć lista obrazów (obrazy o rozmiarze 16 x 16 pikseli) używana przez zarówno mały Widok ikon kontrolki widok listy, jak i elementy nagłówka kontrolki widoku listy.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHeaderCtrl](../mfc/using-cheaderctrl.md)
