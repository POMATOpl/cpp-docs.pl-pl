---
description: 'Dowiedz się więcej o: style kontrolek suwaka'
title: Style formantu suwaka
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: cec057683862212a4d999ec7d0488c5f2a0837cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216915"
---
# <a name="slider-control-styles"></a>Style formantu suwaka

Kontrolki suwaka ([Korzystanie CSliderCtrl](../mfc/reference/csliderctrl-class.md)) mogą mieć orientację pionową lub poziomą. Mogą mieć znaczniki po obu stronach, obu stron lub żadnej z nich. Mogą one również służyć do określania zakresu kolejnych wartości. Te właściwości są kontrolowane za pomocą stylów kontrolki suwak, które są określane podczas tworzenia kontrolki suwaka.

Style TBS_HORZ i TBS_VERT określają orientację kontrolki suwaka. Jeśli orientacja nie zostanie określona, formant suwaka jest ukierunkowany w poziomie.

Styl TBS_AUTOTICKS tworzy kontrolkę suwaka, która ma znacznik znacznika dla każdego przyrostu w swoim zakresie wartości. Znaczniki te są dodawane automatycznie podczas wywoływania funkcji składowej [SetRange](../mfc/reference/csliderctrl-class.md#setrange) . Jeśli nie określisz TBS_AUTOTICKS, możesz użyć funkcji składowych, takich jak [SetTic](../mfc/reference/csliderctrl-class.md#settic) i [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), aby określić pozycje znaczników. Aby utworzyć kontrolkę suwaka, która nie wyświetla znaczników, można użyć stylu TBS_NOTICKS.

Znaczniki mogą być wyświetlane na jednej lub obu stronach kontrolki suwaka. Dla suwaków poziomych można określić styl TBS_BOTTOM lub TBS_TOP. W przypadku kontrolek pionowego suwaka można określić styl TBS_RIGHT lub TBS_LEFT. (TBS_BOTTOM i TBS_RIGHT są ustawieniami domyślnymi). Dla znaczników osi po obu stronach kontrolki suwaka w dowolnej orientacji określ styl TBS_BOTH.

Kontrolka suwaka może wyświetlać zakres wyboru tylko w przypadku określenia stylu TBS_ENABLESELRANGE podczas jego tworzenia. Gdy kontrolka suwak ma ten styl, znaczniki w początkowym i końcowym miejscu zakresu wyboru są wyświetlane jako trójkąty (zamiast kresek pionowych), a zakres wyboru jest wyróżniony. Na przykład zakresy wyboru mogą być przydatne w prostej aplikacji do planowania. Użytkownik może wybrać zakres znaczników odpowiadający godzinom w ciągu dnia, aby zidentyfikować zaplanowany czas spotkania.

Domyślnie długość suwaka kontrolki suwaka różni się w zależności od zmiany zakresu zaznaczenia. Jeśli kontrolka suwaka ma styl TBS_FIXEDLENGTH, Długość suwaka pozostaje taka sama nawet wtedy, gdy zmieni się zakres zaznaczenia. Kontrolka suwaka z stylem TBS_NOTHUMB nie zawiera suwaka.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
