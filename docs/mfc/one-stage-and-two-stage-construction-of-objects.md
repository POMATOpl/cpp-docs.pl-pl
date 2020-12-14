---
description: 'Dowiedz się więcej na temat: One-Stage i Two-Stage konstruowania obiektów'
title: Jedno- i dwuetapowa konstrukcja obiektów
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: d46a8d380c263c4ce18671f02b11d5b058bc8410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243916"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Jedno- i dwuetapowa konstrukcja obiektów

Istnieje wybór między dwiema technikami tworzenia obiektów graficznych, takich jak pióra i pędzle:

- *Konstrukcja jednoetapowa*: Konstruuj i zainicjuj obiekt w jednym etapie, wszystko z konstruktorem.

- *Konstrukcja dwuetapowa*: Konstruowanie i inicjowanie obiektu w dwóch oddzielnych etapach. Konstruktor tworzy obiekt i inicjuje go funkcja inicjująca.

Konstrukcja dwuetapowa jest zawsze bezpieczniejsza. W konstrukcji jednoetapowej Konstruktor może zgłosić wyjątek, jeśli podano nieprawidłowe argumenty lub alokacja pamięci nie powiedzie się. Ten problem można uniknąć przez konstrukcję dwuetapową, chociaż trzeba sprawdzić obecność błędów. W obu przypadkach zniszczenie obiektu jest tym samym procesem.

> [!NOTE]
> Te techniki mają zastosowanie do tworzenia dowolnych obiektów, a nie tylko obiektów graficznych.

## <a name="example-of-both-construction-techniques"></a>Przykład obu technik konstrukcyjnych

W poniższym przykładzie przedstawiono obie metody konstruowania obiektu pióra:

[!code-cpp[NVC_MFCDocViewSDI#6](codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Obiekty graficzne](graphic-objects.md)

- [Wybieranie obiektu graficznego do kontekstu urządzenia](selecting-a-graphic-object-into-a-device-context.md)

- [Konteksty urządzenia](device-contexts.md)

- [Rysowanie w widoku](drawing-in-a-view.md)

## <a name="see-also"></a>Zobacz też

[Obiekty graficzne](graphic-objects.md)
