---
description: Dowiedz się więcej o tym, jak zapewnić aktywację Flicker-Free
title: Zapewnianie aktywacji pozbawionej migotania
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: c0af1ccdd4795f55296ff38e0e74bc6492f79eb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248830"
---
# <a name="providing-flicker-free-activation"></a>Zapewnianie aktywacji pozbawionej migotania

Jeśli kontrolka narysuje się identycznie w stanie nieaktywnym i aktywnym (i nie korzysta z aktywacji bez okien), można wyeliminować operacje rysowania i towarzyszące Migotanie wizualne, które zwykle występuje podczas dokonywania przejścia między Stanami nieaktywnym i aktywnym. W tym celu należy uwzględnić flagę **noFlickerActivate** w zestawie flag zwracanych przez [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Na przykład:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

Kod do uwzględnienia tej flagi jest generowany automatycznie, jeśli wybrano opcję **aktywacji bez migotania** na stronie [Ustawienia kontroli](../mfc/reference/control-settings-mfc-activex-control-wizard.md) podczas tworzenia kontrolki za pomocą Kreatora kontrolek ActiveX MFC.

W przypadku korzystania z funkcji aktywacji bezokienkowej Ta optymalizacja nie ma żadnego wpływu.

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC: Optymalizacja](../mfc/mfc-activex-controls-optimization.md)
