---
description: 'Dowiedz się więcej o: Instrukcje: ładowanie zasobu wstążki z aplikacji MFC'
title: 'Porady: ładowanie zasobu wstążki z aplikacji MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 231acbd475bf84b2623eb44f9a3500ab94145d06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330199"
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
