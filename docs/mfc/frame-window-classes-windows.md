---
description: 'Dowiedz się więcej na temat: klasy okien ramowych (Windows)'
title: Klasy okien ramowych (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: dcd7dea1fd138fbe2ebf3f82013b00cff5ff1f52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339712"
---
# <a name="frame-window-classes-windows"></a>Klasy okien ramowych (Windows)

Okna ramowe są oknami zawierającymi ramki aplikacji lub części aplikacji. Okna ramowe zwykle zawierają inne okna, takie jak widoki, paski narzędzi i paski stanu. W przypadku `CMDIFrameWnd` , mogą one zawierać `CMDIChildWnd` obiekty pośrednie.

[CFrameWnd](reference/cframewnd-class.md)<br/>
Klasa bazowa dla głównego okna ramki aplikacji SDI. Również Klasa bazowa dla wszystkich innych klas okien ramowych.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
Klasa bazowa dla głównego okna ramki aplikacji MDI.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
Klasa bazowa dla okien ramowych dokumentu aplikacji MDI.

[CMiniFrameWnd](reference/cminiframewnd-class.md)<br/>
Okno ramki o połowie wysokości zwykle pojawia się wokół przestawnych pasków narzędzi.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Udostępnia okno ramek dla widoku, gdy dokument serwera jest edytowany w miejscu.

## <a name="related-class"></a>Powiązana Klasa

Klasa `CMenu` udostępnia interfejs, za który uzyskuje dostęp do menu aplikacji. Jest to przydatne do dynamicznego manipulowania menu w czasie wykonywania; na przykład podczas dodawania lub usuwania elementów menu zgodnie z kontekstem. Mimo że menu są najczęściej używane w oknach ramowych, mogą być również używane z oknami dialogowymi i innymi oknami niepodrzędnymi.

[CMenu](reference/cmenu-class.md)<br/>
Hermetyzuje `HMENU` uchwyt na pasku menu aplikacji i wyskakujących menu.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
