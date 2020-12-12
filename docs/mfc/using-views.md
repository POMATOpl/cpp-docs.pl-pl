---
description: 'Dowiedz się więcej na temat: korzystanie z widoków'
title: Używanie widoków
ms.date: 11/04/2016
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
ms.openlocfilehash: f17855c1389da44630a21830033c4457db6e3703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236649"
---
# <a name="using-views"></a>Używanie widoków

Obowiązkiem widoku jest wyświetlenie danych dokumentu w sposób graficzny i zaakceptowanie i interpretacja przez użytkownika operacji na dokumencie. Zadania wykonywane podczas pisania klasy widoku są następujące:

- Napisz funkcję członkowską [OnDraw](../mfc/reference/cview-class.md#ondraw) klasy widoku, która renderuje dane dokumentu.

- Łączenie odpowiednich komunikatów systemu Windows i obiektów interfejsu użytkownika, takich jak elementy menu do funkcji składowych programu obsługi komunikatów w klasie widoku.

- Zaimplementuj te procedury obsługi, aby interpretować dane wejściowe użytkownika.

Ponadto może być konieczne przesłonięcie innych `CView` funkcji Członkowskich w klasie widoku pochodnego. W szczególności można chcieć przesłonić [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) w celu przeprowadzenia specjalnej inicjalizacji widoku i [OnUpdate](../mfc/reference/cview-class.md#onupdate) w celu wykonania specjalnego przetwarzania, które jest wymagane tuż przed ponownym narysowaniem widoku. W przypadku dokumentów wielostronicowych należy również przesłonić [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) w celu zainicjowania okna dialogowego drukowanie z liczbą stron do drukowania i innych informacji. Aby uzyskać więcej informacji na temat przesłaniania `CView` funkcji Członkowskich, zobacz Klasa [CView](../mfc/reference/cview-class.md) w *dokumentacji MFC*.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Pochodne klasy widoków dostępne w MFC](../mfc/derived-view-classes-available-in-mfc.md)

- [Rysowanie w widoku](../mfc/drawing-in-a-view.md)

- [Interpretowanie danych wprowadzonych przez użytkownika za pośrednictwem widoku](../mfc/interpreting-user-input-through-a-view.md)

- [Rola widoku w drukowaniu](../mfc/role-of-the-view-in-printing.md)

- [Przewijanie i skalowanie widoków](../mfc/scrolling-and-scaling-views.md)

- [Inicjowanie i oczyszczanie dokumentów i widoków](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Zobacz też

[Architektura dokumentu/widoku](../mfc/document-view-architecture.md)<br/>
[Klasa CFormView](../mfc/reference/cformview-class.md)<br/>
[Widoki rekordów (dostęp do danych MFC)](../data/record-views-mfc-data-access.md)<br/>
[Pomijanie mechanizmu serializacji](../mfc/bypassing-the-serialization-mechanism.md)
