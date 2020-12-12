---
description: 'Dowiedz się więcej na temat: używanie kontrolki wspólnej jako okna podrzędnego'
title: Używanie formantu wspólnego jako okna podrzędnego
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 5a5fda2cbf8d0bf16ccb17f2766b31d24e5c0c67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263559"
---
# <a name="using-a-common-control-as-a-child-window"></a>Używanie formantu wspólnego jako okna podrzędnego

Każdy z formantów wspólnych systemu Windows może być używany jako okno podrzędne dowolnego innego okna. Poniższa procedura opisuje sposób dynamicznego tworzenia kontrolki, a następnie pracy z nią.

### <a name="to-use-a-common-control-as-a-child-window"></a>Aby użyć formantu wspólnego jako okna podrzędnego

1. Zdefiniuj formant w powiązanej klasie lub obsłudze.

1. Użyj przesłonięcia kontrolki [CWnd:: Create](../mfc/reference/cwnd-class.md#create) w celu utworzenia formantu systemu Windows.

1. Po utworzeniu kontrolki (jak wcześniej jako `OnCreate` procedura obsługi w przypadku podklasy kontrolki) można manipulować formantem za pomocą jego funkcji składowych. Aby uzyskać szczegółowe informacje na temat metod, zobacz opisy poszczególnych kontrolek w [kontrolce](../mfc/controls-mfc.md) .

1. Po zakończeniu kontroli Użyj [CWnd::D estroywindow](../mfc/reference/cwnd-class.md#destroywindow) , aby zniszczyć formant.

## <a name="see-also"></a>Zobacz też

[Tworzenie i używanie kontrolek](../mfc/making-and-using-controls.md)<br/>
[Formanty](../mfc/controls-mfc.md)
