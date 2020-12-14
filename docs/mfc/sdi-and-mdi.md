---
description: 'Dowiedz się więcej na temat: SDI i MDI'
title: SDI i MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: bfa54db04a657507b4b491ada6e8f08d17c2d1c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217786"
---
# <a name="sdi-and-mdi"></a>SDI i MDI

MFC ułatwia współpracę z interfejsem jednostronicowym (SDI) i aplikacjami interfejsu wielu dokumentów (MDI).

Aplikacje SDI umożliwiają jednoczesne wyświetlanie tylko jednego otwartego okna ramki dokumentu. Aplikacje MDI umożliwiają otwieranie wielu okien ramowych dokumentu w tym samym wystąpieniu aplikacji. Aplikacja MDI zawiera okno, w którym można otwierać wiele okien podrzędnych MDI, które są samymi oknami z ramkami, z których każdy zawiera oddzielny dokument. W niektórych aplikacjach okna podrzędne mogą mieć różne typy, takie jak okna wykresów i okna arkusza kalkulacyjnego. W takim przypadku pasek menu może ulec zmianie, ponieważ są aktywowane okna podrzędne MDI różnych typów.

> [!NOTE]
> W systemie Windows 95 i nowszych aplikacje są zwykle SDI, ponieważ system operacyjny przyjął widok "dokumenty wyśrodkowane".

Aby uzyskać więcej informacji, zobacz [dokumenty, widoki i struktura](../mfc/documents-views-and-the-framework.md).

## <a name="see-also"></a>Zobacz też

[Używanie klas do pisania aplikacji dla systemu Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
