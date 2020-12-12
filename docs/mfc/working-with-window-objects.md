---
description: 'Dowiedz się więcej na temat: Praca z obiektami okien'
title: Praca z obiektami okien
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: 4a8c6f2c40eadbfe53aa79683bea29847adf684f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172596"
---
# <a name="working-with-window-objects"></a>Praca z obiektami okien

Praca z wywołaniami systemu Windows dla dwóch rodzajów działań:

- Obsługa komunikatów systemu Windows

- Rysowanie w oknie

Aby obsłużyć komunikaty systemu Windows w dowolnym oknie, w tym własne okna podrzędne, zobacz [Mapowanie komunikatów do funkcji](../mfc/reference/mapping-messages-to-functions.md) w celu mapowania komunikatów do klasy okna języka C++. Następnie Zapisz funkcje członkowskie programu obsługi komunikatów w klasie.

Większość rysunków w aplikacji Framework występuje w widoku, którego funkcja członkowska [OnDraw](../mfc/reference/cview-class.md#ondraw) jest wywoływana za każdym razem, gdy zawartość okna musi być narysowana. Jeśli okno jest elementem podrzędnym widoku, można delegować część rysowania widoku do okna podrzędnego, `OnDraw` wywołując jedno z funkcji składowych okna.

W każdym przypadku potrzebny będzie kontekst urządzenia do rysowania. Możesz użyć pióra, pędzla i innych obiektów graficznych zawartych w kontekście urządzenia skojarzonym z oknem. Można też zmodyfikować te obiekty, aby uzyskać potrzebne efekty rysowania. Po skonfigurowaniu kontekstu urządzenia należy wywoływać funkcje składowe klasy [przechwytywania](../mfc/reference/cdc-class.md) (klasy kontekstu urządzenia) do rysowania linii, kształtów i tekstu; Aby używać kolorów; i do pracy z systemem współrzędnych.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Obsługa i mapowanie komunikatów](../mfc/message-handling-and-mapping.md)

- [Rysowanie w widoku](../mfc/drawing-in-a-view.md)

- [Konteksty urządzenia](../mfc/device-contexts.md)

- [Obiekty graficzne](../mfc/graphic-objects.md)

## <a name="see-also"></a>Zobacz też

[Obiekty okna](../mfc/window-objects.md)
