---
description: 'Dowiedz się więcej na temat: Kiedy inicjować obiekty CWnd'
title: Kiedy inicjować obiekty CWnd
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: 89d40b826507574fddd41364ac6cecc526663519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142769"
---
# <a name="when-to-initialize-cwnd-objects"></a>Kiedy inicjować obiekty CWnd

Nie można utworzyć własnych okien podrzędnych lub wywołać dowolnych funkcji interfejsu API systemu Windows w konstruktorze `CWnd` obiektu pochodnego. Dzieje się tak, ponieważ `HWND` dla `CWnd` obiektu nie został jeszcze utworzony. Większość inicjowania specyficznych dla systemu Windows, takich jak dodawanie okien podrzędnych, musi zostać wykonana w programie obsługi komunikatów [OnCreate](../mfc/reference/cwnd-class.md#oncreate) .

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Tworzenie okien ramowych dokumentu](../mfc/creating-document-frame-windows.md)

- [Tworzenie dokumentu/widoku](../mfc/document-view-creation.md)

## <a name="see-also"></a>Zobacz też

[Korzystanie z okien ramowych](../mfc/using-frame-windows.md)
