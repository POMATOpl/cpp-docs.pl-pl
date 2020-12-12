---
description: Dowiedz się więcej na temat dostosowywania elementu nagłówka&#39;wyglądu
title: Dostosowywanie wyglądu elementu nagłówka&#39;s
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 9cddb0f30dc2b7183952bd114990d1a608782ec3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309371"
---
# <a name="customizing-the-header-item39s-appearance"></a>Dostosowywanie wyglądu elementu nagłówka&#39;s

Ustawiając parametr *dwStyle* podczas pierwszego tworzenia kontrolki nagłówka ([CHeaderCtrl:: Create](reference/cheaderctrl-class.md#create)), można zdefiniować wygląd i zachowanie elementów nagłówka lub samego formantu nagłówka.

Poniżej znajduje się próbkowanie stylów, które można ustawić, i ich przeznaczenie:

- Aby element nagłówka wyglądał jak przycisk, użyj stylu **HDS_BUTTONS** .

   Użyj tego stylu, jeśli chcesz wykonać akcje w odpowiedzi na kliknięcia myszą w elemencie nagłówka, takim jak sortowanie danych według określonej kolumny, tak jak w programie Microsoft Outlook.

- Aby nadać elementom nagłówka "śledzenie gorąca", gdy kursor myszy przesuwa się nad nimi, użyj stylu **HDS_HOTTRACK** .

   Śledzenie gorąca wyświetla konspekt 3D, gdy wskaźnik przechodzi nad elementem na płaskim pasku w przeciwnym przypadku.

- Aby wskazać, że formant nagłówka powinien być ukryty, użyj stylu **HDS_HIDDEN** .

   Styl **HDS_HIDDEN** wskazuje, że formant nagłówka jest przeznaczony do użycia jako kontener danych, a nie do kontrolki wizualnej. Ten styl nie ukrywa automatycznie formantu, ale zamiast tego wpływa na zachowanie `CHeaderCtrl::Layout` . Wartość zwrócona przez element członkowski *cy* `WINDOWPOS` struktury będzie równa zero, co oznacza, że formant nie powinien być widoczny dla użytkownika.

Aby uzyskać więcej informacji o tych właściwościach, zobacz [elementy](/windows/win32/Controls/header-controls) w Windows SDK. Aby uzyskać informacje o dodawaniu elementów do kontrolki nagłówka, zobacz [Dodawanie elementów do formantu nagłówka](adding-items-to-the-header-control.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHeaderCtrl](using-cheaderctrl.md)<br/>
[Formanty](controls-mfc.md)
