---
description: 'Dowiedz się więcej na temat: wprowadzenie do klas okien ATL'
title: Wprowadzenie do klas okien ATL
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 54a9d9764450025e51f9fac368a3434ca786fe09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152727"
---
# <a name="introduction-to-atl-window-classes"></a>Wprowadzenie do klas okien ATL

Następujące klasy ATL zostały zaprojektowane w celu zaimplementowania systemu Windows i manipulowania nim:

- [CWindow](../atl/reference/cwindow-class.md) umożliwia dołączenie uchwytu okna do `CWindow` obiektu. Następnie należy wywołać `CWindow` metody do manipulowania oknem.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) umożliwia zaimplementowanie nowego okna i przetwarzanie komunikatów przy użyciu mapy komunikatów. Okno można utworzyć na podstawie nowej klasy systemu Windows, superklasy istniejącej klasy lub podklasy istniejącego okna.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) umożliwia implementowanie modalnych lub niemodalnych okien dialogowych oraz przetwarzanie komunikatów przy użyciu mapy komunikatów.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) jest prezbudowaną klasą, która implementuje okno, którego mapa wiadomości znajduje się w innej klasie. Korzystanie z programu `CContainedWindowT` pozwala na scentralizowanie przetwarzania komunikatów w jednej klasie.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) umożliwia zaimplementowanie okna dialogowego (modalne lub niemodalne), które obsługuje kontrolki ActiveX.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) umożliwia zaimplementowanie modalnego okna dialogowego z podstawowymi funkcjami.

- [CAxWindow](../atl/reference/caxwindow-class.md) umożliwia wdrożenie okna, które obsługuje kontrolkę ActiveX.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) umożliwia wdrożenie okna, które obsługuje licencjonowane kontrolki ActiveX.

Oprócz określonych klas okien, ATL oferuje kilka klas zaprojektowanych w celu ułatwienia implementacji obiektu okna ATL. Są one następujące:

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) zarządza informacjami o nowej klasie okna.

- [CWinTraits](../atl/reference/cwintraits-class.md) i [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) zapewniają prostą metodę standaryzacji cech obiektu okna ATL.

## <a name="see-also"></a>Zobacz też

[Klasy okien](../atl/atl-window-classes.md)
