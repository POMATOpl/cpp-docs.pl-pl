---
description: 'Dowiedz się więcej o: zapewnianie interakcji z myszą przy nieaktywnym'
title: Zapewnianie interakcji z myszą przy braku aktywności
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: bd3c069b052b58059de5f311e4ead795400d32fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248739"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Zapewnianie interakcji z myszą przy braku aktywności

Jeśli formant nie zostanie natychmiast aktywowany, można nadal chcieć przetworzyć WM_SETCURSOR i WM_MOUSEMOVE komunikatów, nawet jeśli kontrolka nie ma własnego okna. Można to osiągnąć przez włączenie `COleControl` implementacji `IPointerInactive` interfejsu, który jest domyślnie wyłączony. (Zobacz *zestaw SDK ActiveX* , aby uzyskać opis tego interfejsu). Aby ją włączyć, należy uwzględnić flagę pointerInactive w zestawie flag zwracanych przez [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

Kod do uwzględnienia tej flagi jest generowany automatycznie po wybraniu opcji **powiadomienia wskaźnika myszy, gdy opcja nieaktywna** na stronie [Ustawienia kontroli](../mfc/reference/control-settings-mfc-activex-control-wizard.md) podczas tworzenia kontrolki za pomocą **Kreatora kontrolek ActiveX MFC**.

Po `IPointerInactive` włączeniu interfejsu program deleguje kontener WM_SETCURSOR i WM_MOUSEMOVE do niego komunikatów. `COleControl`Implementacja `IPointerInactive` wysyłania komunikatów przez mapę komunikatów kontrolki po dopasowaniu odpowiednio współrzędnych myszy. Możesz przetwarzać komunikaty podobnie jak zwykłe komunikaty okna przez dodanie odpowiednich wpisów do mapy komunikatów. W przypadku obsługi tych komunikatów należy unikać używania *m_hWnd* zmiennej składowej (lub żadnej funkcji składowej, która go używa) bez uprzedniego sprawdzenia, czy jej wartość nie jest **równa null**.

Możesz również mieć nieaktywną kontrolkę jako obiekt docelowy operacji przeciągania i upuszczania OLE. Wymaga to aktywowania kontrolki w momencie, gdy użytkownik przeciągnie obiekt nad nim, aby okno kontrolki było rejestrowane jako miejsce docelowe upuszczania. Aby spowodować, że aktywacja wystąpi podczas przeciągania, Przesłoń [COleControl:: GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)i zwróć flagę POINTERINACTIVE_ACTIVATEONDRAG:

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

Włączenie `IPointerInactive` interfejsu zazwyczaj oznacza, że kontrolka ma mieć możliwość przetwarzania komunikatów myszy przez cały czas. Aby uzyskać to zachowanie w kontenerze, który nie obsługuje `IPointerInactive` interfejsu, musisz mieć formant zawsze aktywowany, gdy jest widoczny, co oznacza, że kontrolka powinna zawierać flagę OLEMISC_ACTIVATEWHENVISIBLE między jej różnymi flagami. Aby jednak zapobiec wprowadzeniu tej flagi do kontenera, który obsługuje `IPointerInactive` , można również określić flagę OLEMISC_IGNOREACTIVATEWHENVISIBLE:

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC: Optymalizacja](../mfc/mfc-activex-controls-optimization.md)
