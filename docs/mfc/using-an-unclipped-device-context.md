---
description: Dowiedz się więcej o tym, jak używać nieprzycinanego kontekstu urządzenia
title: Używanie nieobcinanego kontekstu urządzenia
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 76131d35b108b04caf0b07be8c46e250120f9f62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202642"
---
# <a name="using-an-unclipped-device-context"></a>Używanie nieobcinanego kontekstu urządzenia

Jeśli nie masz absolutnej pewności, że formant nie jest malowany poza jego prostokątem klienta, możesz zrealizować mały, ale wykrywalny wzrost, wyłączając wywołanie `IntersectClipRect` , które jest wykonywane przez `COleControl` . Aby to zrobić, Usuń flagę *clipPaintDC* z zestawu flag zwracanych przez [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Na przykład:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

Kod do usunięcia tej flagi jest generowany automatycznie po wybraniu opcji **kontekstu urządzenia nieprzycinanego** na stronie [Ustawienia kontroli](../mfc/reference/control-settings-mfc-activex-control-wizard.md) podczas tworzenia kontrolki za pomocą Kreatora kontrolek ActiveX MFC.

W przypadku korzystania z funkcji aktywacji bezokienkowej Ta optymalizacja nie ma żadnego wpływu.

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC: Optymalizacja](../mfc/mfc-activex-controls-optimization.md)
