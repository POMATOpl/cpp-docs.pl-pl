---
description: 'Dowiedz się więcej o programie: korzystanie z okna'
title: Korzystanie z okna (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: fb9f1e03a27ad8b637da30eacbd100daf920cdb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157283"
---
# <a name="using-a-window"></a>Korzystanie z okna

Klasa [CWindow](../atl/reference/cwindow-class.md) umożliwia korzystanie z okna. Po dołączeniu okna do `CWindow` obiektu można wywołać `CWindow` metody do manipulowania oknem. `CWindow` zawiera również operator HWND, aby przekonwertować `CWindow` obiekt na Właściwość HWND. W ten sposób można przekazać `CWindow` obiekt do dowolnej funkcji, która wymaga dojścia do okna. Można łatwo mieszać `CWindow` wywołania metod i wywołania funkcji Win32 bez tworzenia żadnych obiektów tymczasowych.

Ponieważ `CWindow` ma tylko dwa składowe danych (uchwyt okna i domyślne wymiary), nie nakłada na kod. Ponadto wiele `CWindow` metod po prostu zawija odpowiednie funkcje Win32 API. Przy użyciu `CWindow` , element członkowski HWND jest automatycznie przenoszona do funkcji Win32.

Oprócz `CWindow` bezpośredniego używania, można również od niego dziedziczyć, aby dodać dane lub kod do klasy. Sama ATL dziedziczy trzy klasy z `CWindow` : [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md)i [CContainedWindowT](../atl/using-contained-windows.md).

## <a name="see-also"></a>Zobacz też

[Klasy okien](../atl/atl-window-classes.md)
