---
description: 'Dowiedz się więcej o programie: Menedżer wizualizacji'
title: Menedżer wizualizacji
ms.date: 11/19/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: b99331503e4e7e69cc5d8a19fde7641c1b1daeeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143211"
---
# <a name="visualization-manager"></a>Menedżer wizualizacji

Visual Manager jest obiektem, który steruje wyglądem całej aplikacji. Pełni rolę pojedynczej klasy, w której można umieścić cały kod rysowania aplikacji. Biblioteka MFC zawiera kilku menedżerów wizualizacji. Możesz również utworzyć własny Menedżer wizualizacji, jeśli chcesz utworzyć niestandardowy widok dla swojej aplikacji. Następujące obrazy przedstawiają tę samą aplikację, gdy są włączone różne menedżerów wizualnych:

![MojaApl jako renderowany przez CMFCVisualManagerWindows](../mfc/media/vmwindows.png "MojaApl jako renderowany przez CMFCVisualManagerWindows") <br/>
MojaApl korzystający z programu CMFCVisualManagerWindows Manager

![MojaApl jako renderowany przez CMFCVisualManagerVS2005](../mfc/media/vmvs2005.png "MojaApl jako renderowany przez CMFCVisualManagerVS2005") <br/>
MojaApl korzystający z programu CMFCVisualManagerVS2005 Manager

![MojaApl jako renderowany przez CMFCVisualManagerOfficeXP](../mfc/media/vmofficexp.png "MojaApl jako renderowany przez CMFCVisualManagerOfficeXP") <br/>
MojaApl korzystający z programu CMFCVisualManagerOfficeXP Manager

![MojaApl jako renderowany przez CMFCVisualManagerOffice2003](../mfc/media/vmoffice2003.png "MojaApl jako renderowany przez CMFCVisualManagerOffice2003") <br/>
MojaApl korzystający z programu CMFCVisualManagerOffice2003 Manager

![MojaApl jako renderowany przez CMFCVisualManagerOffice2007](../mfc/media/msoffice2007.png "MojaApl jako renderowany przez CMFCVisualManagerOffice2007") <br/>
MojaApl korzystający z programu CMFCVisualManagerOffice2007 Manager

Domyślnie program Visual Manager utrzymuje kod rysowania dla kilku elementów graficznego interfejsu użytkownika. Aby zapewnić niestandardowe elementy interfejsu użytkownika, należy zastąpić powiązane metody rysowania programu Visual Manager. Aby zapoznać się z listą tych metod, zobacz [Klasa CMFCVisualManager](../mfc/reference/cmfcvisualmanager-class.md). Metody, które można przesłonić w celu zapewnienia niestandardowego wyglądu, to wszystkie metody, które zaczynają się od `OnDraw` .

Aplikacja może mieć tylko jeden `CMFCVisualManager` obiekt. Aby uzyskać wskaźnik do Menedżera wizualizacji dla aplikacji, wywołaj funkcję statyczną [CMFCVisualManager:: GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Ponieważ wszyscy menedżerowie wizualizacji dziedziczą z `CMFCVisualManager` , `CMFCVisualManager::GetInstance` Metoda otrzyma wskaźnik do odpowiedniego Menedżera wizualizacji, nawet jeśli utworzysz niestandardowy program Visual Manager.

Jeśli chcesz utworzyć niestandardowy Menedżer wizualizacji, musisz poprowadzić go z Menedżera Visual, który już istnieje. Domyślną klasą pochodną jest `CMFCVisualManager` . Można jednak użyć innego programu Visual Manager, jeśli jest lepiej podobny do tego, czego potrzebujesz w aplikacji. Na przykład jeśli chciałeś użyć `CMFCVisualManagerOffice2007` Menedżera wizualizacji, ale chciałeś tylko zmienić sposób wyglądu separatorów, możesz utworzyć klasę niestandardową z `CMFCVisualManagerOffice2007` . W tym scenariuszu należy zastąpić tylko metody dla separatorów rysowania.

Istnieją dwa sposoby używania określonego programu Visual Manager dla aplikacji. Jednym ze sposobów jest wywołanie metody [CMFCVisualManager:: SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) i przekazanie odpowiedniego Menedżera wizualizacji jako parametru. Poniższy przykład kodu pokazuje, jak używać programu `CMFCVisualManagerVS2005` Visual Manager z tą metodą:

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

Innym sposobem korzystania z Menedżera wizualizacji w aplikacji jest ręczne utworzenie go. Aplikacja będzie używać tego nowego programu Visual Manager do wszystkich renderingów. Jednak ponieważ może istnieć tylko jeden `CMFCVisualManager` obiekt dla każdej aplikacji, przed utworzeniem nowego programu Visual Manager trzeba będzie usunąć bieżącego. W poniższym przykładzie `CMyVisualManager` jest to niestandardowy program Visual Manager pochodzący z `CMFCVisualManager` . Poniższa metoda zmieni, jakiego programu Visual Manager używa do wyświetlania aplikacji, w zależności od indeksu:

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
        CMFCVisualManager::GetInstance();
        break;

    case CUSTOM_STYLE:
        new CMyVisualManager;
        break;

    default:
        CMFCVisualManager::GetInstance();
        break;
    }

    CMFCVisualManager::GetInstance()->RedrawAll();
}
```

## <a name="see-also"></a>Zobacz też

[Elementy interfejsu użytkownika](../mfc/user-interface-elements-mfc.md)<br/>
[Klasa CMFCVisualManager](../mfc/reference/cmfcvisualmanager-class.md)
