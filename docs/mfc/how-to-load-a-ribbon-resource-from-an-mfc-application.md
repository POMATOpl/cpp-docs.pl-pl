---
title: 'Porady: ładowanie zasobu wstążki z aplikacji MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 47a3b94bbcb14c6c2923524db1f6a83b687e50e8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626399"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Porady: ładowanie zasobu wstążki z aplikacji MFC

Aby użyć zasobu wstążki w aplikacji, należy zmodyfikować aplikację w celu załadowania zasobu wstążki.

### <a name="to-load-a-ribbon-resource"></a>Aby załadować zasób wstążki

1. Zadeklaruj `Ribbon Control` obiekt w `CMainFrame` klasie.

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. W programie `CMainFrame::OnCreate` Utwórz i zainicjuj kontrolkę wstążki.

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>Zobacz też

[Projektant wstążki (MFC)](ribbon-designer-mfc.md)
