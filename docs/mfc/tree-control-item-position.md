---
description: 'Dowiedz się więcej na temat: położenie elementu kontrolki drzewa'
title: Położenie elementu formantu drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: 7eeab82c48344f7e16a31b8d6962007024277dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264076"
---
# <a name="tree-control-item-position"></a>Położenie elementu formantu drzewa

Pozycja początkowa elementu jest ustawiana, gdy element zostanie dodany do formantu drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) za pomocą `InsertItem` funkcji składowej. Wywołanie funkcji składowej określa uchwyt elementu nadrzędnego i uchwyt elementu, po którym ma zostać wstawiony nowy element. Drugie dojście musi identyfikować element podrzędny danego elementu nadrzędnego lub jedną z następujących wartości: `TVI_FIRST` , `TVI_LAST` , lub `TVI_SORT` .

Gdy `TVI_FIRST` lub `TVI_LAST` jest określony, formant drzewa umieszcza nowy element na początku lub na końcu listy elementów podrzędnych elementu nadrzędnego. Gdy `TVI_SORT` jest określony, formant drzewa wstawia nowy element do listy elementów podrzędnych w kolejności alfabetycznej na podstawie tekstu etykiet elementów.

Możesz umieścić listę elementów podrzędnych elementu nadrzędnego w kolejności alfabetycznej, wywołując funkcję elementu członkowskiego [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) . Ta funkcja zawiera parametr, który określa, czy wszystkie poziomy elementów podrzędnych malejąco od danego elementu nadrzędnego są również sortowane w kolejności alfabetycznej.

Funkcja członkowska [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) umożliwia sortowanie elementów podrzędnych na podstawie kryteriów zdefiniowanych przez użytkownika. Po wywołaniu tej funkcji należy określić funkcję wywołania zwrotnego zdefiniowanego przez aplikację, którą formant drzewa może wywołać, gdy zostanie podjęta określona kolejność względna dwóch elementów podrzędnych. Funkcja wywołania zwrotnego otrzymuje 2 32-bitowe wartości zdefiniowane przez aplikację dla porównywanych elementów i trzecią wartość 32-bitową określoną podczas wywoływania `SortChildrenCB` .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
