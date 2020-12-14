---
description: 'Dowiedz się więcej na temat: Wybieranie obiektu graficznego do kontekstu urządzenia'
title: Wybieranie obiektu graficznego do kontekstu urządzenia
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: cc2aabbcb1614fc77e5eadf9e6fba13ba377a4c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217682"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Wybieranie obiektu graficznego do kontekstu urządzenia

Ten temat ma zastosowanie do używania obiektów graficznych w kontekście urządzenia okna. Po [utworzeniu obiektu rysowania](../mfc/one-stage-and-two-stage-construction-of-objects.md)należy zaznaczyć go w kontekście urządzenia zamiast domyślnego obiektu przechowywanego w tym miejscu:

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>Okres istnienia obiektów graficznych

Obiekt graficzny zwrócony przez [polecenie SelectObject](../mfc/reference/cdc-class.md#selectobject) jest "tymczasowy". Oznacza to, że zostanie on usunięty przez funkcję elementu członkowskiego [OnIdle](../mfc/reference/cwinapp-class.md#onidle) klasy `CWinApp` przy następnym czasie bezczynności programu. O ile używasz obiektu zwróconego przez `SelectObject` funkcję w pojedynczej funkcji bez zwracania kontroli do głównej pętli komunikatów, nie będziesz mieć problemu.

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Obiekty graficzne](../mfc/graphic-objects.md)

- [Jednoetapowa i dwuetapowa konstrukcja obiektów graficznych](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Konteksty urządzenia](../mfc/device-contexts.md)

- [Rysowanie w widoku](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Zobacz też

[Obiekty graficzne](../mfc/graphic-objects.md)
