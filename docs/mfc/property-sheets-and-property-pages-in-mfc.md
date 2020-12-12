---
description: 'Dowiedz się więcej o: arkusze właściwości i strony właściwości w MFC'
title: Arkusze właściwości i strony właściwości w MFC
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 93662dcf07e2810ad9f4f51d6df8341f9f6df6dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185430"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>Arkusze właściwości i strony właściwości w MFC

Arkusz właściwości, znany również jako okno dialogowe karty, jest oknem dialogowym zawierającym strony właściwości. Każda Strona właściwości jest oparta na zasobie szablonu okna dialogowego i zawiera formanty. Jest ona zawarta na stronie z kartą w górnej części. Karta nazywa stronę i wskazuje jej przeznaczenie. Użytkownicy klikają kartę w arkuszu właściwości, aby wybrać zestaw kontrolek.

Użyj stron, aby grupować kontrolki w arkuszu właściwości w zrozumiałe zestawy. Arkusz właściwości zawiera zwykle kilka kontrolek. Są one stosowane do wszystkich stron.

Arkusze właściwości opierają się na klasie [CPropertySheet](../mfc/reference/cpropertysheet-class.md). Strony właściwości są oparte na klasie [CPropertyPage](../mfc/reference/cpropertypage-class.md).

Arkusz właściwości jest specjalnym rodzajem okna dialogowego, które jest zwykle używane do modyfikowania atrybutów niektórych zewnętrznych obiektów, takich jak bieżący wybór w widoku. Arkusz właściwości ma trzy główne części: okno dialogowe zawierające, jedną lub kilka stron właściwości, które są wyświetlane pojedynczo, i kartę w górnej części każdej strony, którą użytkownik klika, aby wybrać Tę stronę. Arkusze właściwości są przydatne w sytuacjach, gdy istnieje kilka podobnych grup ustawień lub opcji do zmiany. Arkusz właściwości grupuje informacje w zrozumiały sposób.

> [!NOTE]
> Gdy próbujesz pokazać arkusz właściwości przy użyciu `CPropertySheet::DoModal` , system może wygenerować wyjątek pierwszej szansy. Ten wyjątek występuje, ponieważ system próbuje zmienić [Style okna](../mfc/reference/styles-used-by-mfc.md#window-styles) obiektu przed utworzeniem obiektu. Aby uzyskać więcej informacji o tym wyjątku, a także o tym, jak go uniknąć lub obsłużyć, zobacz [CPropertySheet::D omodal](../mfc/reference/cpropertysheet-class.md#domodal).

## <a name="see-also"></a>Zobacz też

[Arkusze właściwości](../mfc/property-sheets-mfc.md)
