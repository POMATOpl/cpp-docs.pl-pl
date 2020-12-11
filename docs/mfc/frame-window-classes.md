---
description: Dowiedz się więcej na temat Frame-Window klas
title: Klasy okien ramowych
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
ms.openlocfilehash: 888fae71bef2dd2e30e10c645e78ab981a30c6af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154958"
---
# <a name="frame-window-classes"></a>Klasy okien ramowych

Każda aplikacja ma jedno "główne okno ramowe", czyli okno pulpitu, które zwykle zawiera nazwę aplikacji w jej podpisie. Każdy dokument ma zwykle jedno "okno ramki dokumentu". Okno ramki dokumentu zawiera co najmniej jeden widok, który przedstawia dane dokumentu.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Okna ramowe w aplikacjach SDI i MDI

W przypadku aplikacji SDI istnieje jedno okno ramowe pochodzące z klasy [obiektu CFrameWnd](reference/cframewnd-class.md). To okno jest zarówno głównym oknem ramki, jak i oknem ramki dokumentu. W przypadku aplikacji MDI okno głównej ramki pochodzi od klasy [CMDIFrameWnd](reference/cmdiframewnd-class.md), a okna ramki dokumentu, które są oknami podrzędnymi MDI, pochodzą z klasy [CMDIChildWnd](reference/cmdichildwnd-class.md).

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Użyj klasy Frame-Window lub pochodnej

Te klasy zapewniają większość funkcji okna ramki, które są potrzebne dla aplikacji. W normalnych warunkach zachowanie domyślne i ich wygląd będą odpowiadały Twoim potrzebom. Jeśli potrzebujesz dodatkowych funkcji, pochodne od tych klas.

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Klasy okien ramowych tworzone przez Kreatora aplikacji](frame-window-classes-created-by-the-application-wizard.md)

- [Style okna ramowego](frame-window-styles-cpp.md)

- [Zmienianie stylów okna utworzonego przez MFC](changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>Zobacz też

[Okna ramowe](frame-windows.md)
