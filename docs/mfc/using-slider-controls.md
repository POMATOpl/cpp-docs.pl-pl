---
description: 'Dowiedz się więcej na temat: używanie kontrolek suwaka'
title: Używanie formantów suwaka
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
ms.openlocfilehash: b9134d76261bf5c15bfef90260394ee6a4c760e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322664"
---
# <a name="using-slider-controls"></a>Używanie formantów suwaka

Typowym użyciem kontrolki suwaka jest Poniższy wzorzec:

- Formant zostanie utworzony. Jeśli formant jest określony w szablonie okna dialogowego, tworzenie jest automatyczne po utworzeniu okna dialogowego. (W klasie okna dialogowego powinien znajdować się element [Korzystanie CSliderCtrl](../mfc/reference/csliderctrl-class.md) , który odpowiada kontrolce suwaka). Alternatywnie możesz użyć funkcji [Utwórz](../mfc/reference/csliderctrl-class.md#create) element członkowski, aby utworzyć formant jako okno podrzędne dowolnego okna.

- Wywołaj różne funkcje zestawu elementów członkowskich, aby ustawić wartości dla kontrolki. Zmiany, które można wprowadzić, obejmują ustawienie minimalnej i maksymalnej liczby pozycji suwaka, rysowania znaczników, ustawienia zakresu zaznaczenia i zmiany położenia suwaka. W przypadku kontrolek w oknie dialogowym dobry czas, który należy wykonać, jest w funkcji [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) okna dialogowego.

- Gdy użytkownik współdziała z kontrolką, wyśle różne komunikaty powiadomień. Można wyodrębnić wartość suwaka z kontrolki, wywołując funkcję elementu członkowskiego [GetPos](../mfc/reference/csliderctrl-class.md#getpos) .

- Po zakończeniu pracy z kontrolką musisz upewnić się, że jest prawidłowo zniszczona. Jeśli kontrolka suwaka znajduje się w oknie dialogowym, a `CSliderCtrl` obiekt zostanie zniszczony automatycznie. Jeśli nie, musisz upewnić się, że zarówno kontrolka, jak i `CSliderCtrl` obiekt są prawidłowo niszczone.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
