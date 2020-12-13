---
description: 'Dowiedz się więcej na temat: klasy pomocy technicznej systemu Windows'
title: Klasy pomocy technicznej systemu Windows (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: c88a6ef878a428581ca090e78b2fac3b5e02131d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138065"
---
# <a name="windows-support-classes"></a>Klasy pomocy technicznej systemu Windows

Następujące klasy zapewniają obsługę systemu Windows:

- [_U_MENUorID](../atl/reference/u-menuorid-class.md) Udostępnia otoki dla `CreateWindow` i `CreateWindowEx` .

- [CWindow](../atl/reference/cwindow-class.md) Zawiera metody manipulowania oknem. `CWindow` jest klasą bazową dla `CWindowImpl` , `CDialogImpl` , i `CContainedWindow` .

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) Implementuje okno oparte na nowej klasie okna. Umożliwia również podklasa lub Superklasa okna.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) Implementuje okno dialogowe.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) Implementuje okno dialogowe (modalne lub niemodalne), które obsługuje kontrolki ActiveX.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) Implementuje okno dialogowe (modalne lub niemodalne) z podstawowymi funkcjami.

- [CAxWindow](../atl/reference/caxwindow-class.md) Manipuluje oknem, w którym znajduje się kontrolka ActiveX.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) Zapewnia metody manipulowania oknem, które obsługuje kontrolkę ActiveX, a także obsługuje hostowanie kontrolek ActiveX licencjonowanych.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) Implementuje okno zawarte w innym obiekcie.

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) Zarządza informacjami o nowej klasie okna.

- [CDynamicChain](../atl/reference/cdynamicchain-class.md) Obsługuje dynamiczne łączenie map komunikatów.

- [CMessageMap](../atl/reference/cmessagemap-class.md) Umożliwia obiektowi uwidocznienie map komunikatów na innych obiektach.

- [CWinTraits](../atl/reference/cwintraits-class.md) Zapewnia prostą metodę standaryzacji cech obiektu okna ATL.

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) Udostępnia wartości domyślne dla stylów okna i stylów rozszerzonych używanych do tworzenia okna. Te wartości są dodawane przy użyciu operatora logicznego OR do wartości dostarczonych podczas tworzenia okna.

## <a name="related-articles"></a>Powiązane artykuły

[Klasy okien ATL](../atl/atl-window-classes.md)

[Samouczek ATL](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../atl/atl-class-overview.md)<br/>
[Makra mapy komunikatów](../atl/reference/message-map-macros-atl.md)<br/>
[Makra klasy okna](../atl/reference/window-class-macros.md)
