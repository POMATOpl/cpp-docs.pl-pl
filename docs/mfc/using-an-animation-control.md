---
description: 'Dowiedz się więcej na temat: używanie kontrolki animacji'
title: Używanie formantu animacji
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: 7ef4a7b5eb005569ac2a3e3cb66cc0ed785e9299
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202720"
---
# <a name="using-an-animation-control"></a>Używanie formantu animacji

Typowym użyciem kontrolki animacji jest Poniższy wzorzec:

- Formant zostanie utworzony. Jeśli formant jest określony w szablonie okna dialogowego, tworzenie jest automatyczne po utworzeniu okna dialogowego. (W klasie okna dialogowego powinien znajdować się element [Korzystanie CAnimateCtrl](../mfc/reference/canimatectrl-class.md) , który odpowiada kontrolce animacji). Alternatywnie możesz użyć funkcji [Utwórz](../mfc/reference/canimatectrl-class.md#create) element członkowski, aby utworzyć formant jako okno podrzędne dowolnego okna.

- Załaduj klip AVI do kontrolki animacji, wywołując funkcję [Open](../mfc/reference/canimatectrl-class.md#open) member. Jeśli kontrolka animacji znajduje się w oknie dialogowym, dobrym miejscem do wykonania jest w funkcji [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) klasy okna dialogowego.

- Odtwórz klip, wywołując funkcję [odtwarzania](../mfc/reference/canimatectrl-class.md#play) elementu członkowskiego. Jeśli kontrolka animacji znajduje się w oknie dialogowym, dobrym miejscem do wykonania jest funkcja klasy okna dialogowego `OnInitDialog` . Wywołanie `Play` nie jest konieczne, Jeśli kontrolka animacji ma ustawiony styl ACS_AUTOPLAY.

- Jeśli chcesz wyświetlić fragmenty klipu lub odtworzyć ramkę z ramkami, użyj `Seek` funkcji składowej. Aby zatrzymać odtwarzanie klipu, użyj `Stop` funkcji składowej.

- Jeśli nie chcesz od razu zniszczyć formantu, Usuń klip z pamięci, wywołując `Close` funkcję członkowską.

- Jeśli kontrolka animacji znajduje się w oknie dialogowym, a `CAnimateCtrl` obiekt zostanie zniszczony automatycznie. Jeśli nie, musisz upewnić się, że zarówno kontrolka, jak i `CAnimateCtrl` obiekt są prawidłowo niszczone. Niszczenie formantu powoduje automatyczne zamknięcie klipu AVI.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
