---
description: 'Dowiedz się więcej na temat: Tworzenie i wyświetlanie okien dialogowych'
title: Tworzenie i wyświetlanie okien dialogowych
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: 9865e43392021cc7ba1349a73bffb8e47f4cca9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309828"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Tworzenie i wyświetlanie okien dialogowych

Tworzenie obiektu okna dialogowego jest operacją dwuetapową. Najpierw należy skonstruować obiekt okna dialogowego, a następnie utworzyć okno dialogowe. Modalne i Niemodalne okna dialogowe różnią się nieco w procesie używanym do tworzenia i wyświetlania. W poniższej tabeli przedstawiono sposób, w jaki modalne i Niemodalne okna dialogowe są zwykle konstruowane i wyświetlane.

### <a name="dialog-creation"></a>Tworzenie okna dialogowego

|Typ okna dialogowego|Jak go utworzyć|
|-----------------|----------------------|
|[Formularz](creating-modeless-dialog-boxes.md)|Utwórz `CDialog` , a następnie Wywołaj `Create` funkcję członkowską.|
|[Modal](creating-modal-dialog-boxes.md)|Utwórz `CDialog` , a następnie Wywołaj `DoModal` funkcję członkowską.|

W razie potrzeby możesz utworzyć okno dialogowe z [szablonu okna dialogowego w pamięci](using-a-dialog-template-in-memory.md) , który został skonstruowany, a nie z zasobu szablon okna dialogowego. Jest to jednak zaawansowana sekcja.

## <a name="see-also"></a>Zobacz też

[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)
