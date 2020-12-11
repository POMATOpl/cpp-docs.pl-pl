---
description: 'Dowiedz się więcej na temat: Używanie list obrazów w formancie rozszerzonego pola kombi'
title: Używanie list obrazów w formancie rozszerzonego pola kombi
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 9fb4b70f91a8ffc3d0175ec855cd005de10da280
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154373"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Używanie list obrazów w formancie rozszerzonego pola kombi

Główną funkcją formantów rozszerzonego pola kombi jest możliwość kojarzenia obrazów z listy obrazów z poszczególnymi elementami w kontrolce pola kombi. Każdy element jest w stanie wyświetlić trzy różne obrazy: jeden dla wybranego stanu, jeden dla jego stanu niewybranego i trzeci dla obrazu nakładki.

Poniższa procedura kojarzy listę obrazów z rozszerzoną kontrolką pola kombi:

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Aby skojarzyć listę obrazów z rozszerzoną kontrolką pola kombi

1. Utwórz nową listę obrazów (lub Użyj istniejącego obiektu listy obrazów), używając konstruktora [Korzystanie CImageList](../mfc/reference/cimagelist-class.md) i przechowując wynikowy wskaźnik.

1. Zainicjuj nowy obiekt listy obrazów przez wywołanie [Korzystanie CImageList:: Create](../mfc/reference/cimagelist-class.md#create). Poniższy kod jest przykładem tego wywołania.

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. Dodaj opcjonalne obrazy dla każdego możliwego stanu: wybraną lub niewybraną oraz nakładki. Poniższy kod dodaje trzy wstępnie zdefiniowane obrazy.

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. Skojarz listę obrazów z kontrolką z wywołaniem do [Korzystanie CComboBoxEx:: SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).

Po skojarzeniu listy obrazów z formantem można indywidualnie określić obrazy, które będą używane przez każdy element dla trzech możliwych stanów. Aby uzyskać więcej informacji, zobacz [Ustawianie obrazów dla pojedynczego elementu](../mfc/setting-the-images-for-an-individual-item.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Formanty](../mfc/controls-mfc.md)
