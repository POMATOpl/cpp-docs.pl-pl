---
description: 'Dowiedz się więcej na temat: ustawienia kontrolki postępu'
title: Ustawienia formantu postępu
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 0cf3caa5e7b87062b1714f8e5e350840157ff7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217071"
---
# <a name="settings-for-the-progress-control"></a>Ustawienia formantu postępu

Podstawowe ustawienia dla kontrolki postępu ([Korzystanie CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) to zakres i bieżące położenie. Zakres reprezentuje cały czas trwania operacji. Bieżąca pozycja reprezentuje postęp, jaki aplikacja wprowadziła w kierunku ukończenia operacji. Wszelkie zmiany zakresu lub położenia powodują, że formant postępu będzie ponownie rysowany.

Domyślnie zakres jest ustawiony na 0-100, a pozycja początkowa jest ustawiona na 0. Aby pobrać bieżące ustawienia zakresu dla kontrolki postępu, użyj funkcji składowej [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) . Aby zmienić zakres, użyj funkcji składowej [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) .

Aby ustawić pozycję, użyj [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Aby pobrać bieżące położenie bez określania nowej wartości, użyj [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Na przykład możesz chcieć po prostu wykonać zapytanie dotyczące stanu bieżącej operacji.

Aby przejść do bieżącego położenia kontrolki postępu, użyj [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Aby ustawić ilość każdego kroku, użyj [Setkrok](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>Zobacz też

[Korzystanie z CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
