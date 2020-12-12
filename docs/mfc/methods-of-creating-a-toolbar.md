---
description: 'Dowiedz się więcej na temat: metody tworzenia paska narzędzi'
title: Metody tworzenia paska narzędzi
ms.date: 11/04/2016
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
ms.openlocfilehash: 14626f398d3ccabd002cc21be682c1a5616a0410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203084"
---
# <a name="methods-of-creating-a-toolbar"></a>Metody tworzenia paska narzędzi

MFC udostępnia dwie klasy do tworzenia pasków narzędzi: [CToolBar](reference/ctoolbar-class.md) i [CToolBarCtrl](reference/ctoolbarctrl-class.md) (które zawijają interfejs API wspólnego sterowania systemu Windows). `CToolBar` oferuje wszystkie funkcje typowej kontroli nad paskiem narzędzi i obsługuje wiele wymaganych wspólnych ustawień i struktur kontroli. jednak utworzony plik wykonywalny zwykle będzie większy niż ten, który został utworzony za pomocą programu `CToolBarCtrl` .

`CToolBarCtrl` zwykle wynikiem jest mniejszy plik wykonywalny i warto użyć, `CToolBarCtrl` Jeśli nie zamierzasz zintegrować paska narzędzi z architekturą MFC. Jeśli planujesz użycie `CToolBarCtrl` i integrację paska narzędzi w architekturze MFC, musisz zadbać o to, aby przekazywać manipulowanie formantami Toolbar do biblioteki MFC. Ta komunikacja nie jest trudna. Jednak w przypadku korzystania z programu jest to dodatkowa niepotrzebna `CToolBar` .

Visual C++ zapewnia dwa sposoby, aby skorzystać ze wspólnej kontrolki paska narzędzi.

- Utwórz pasek narzędzi przy użyciu `CToolBar` , a następnie Wywołaj [CToolBar:: GetToolBarCtrl](reference/ctoolbar-class.md#gettoolbarctrl) , aby uzyskać dostęp do `CToolBarCtrl` funkcji składowych.

- Utwórz pasek narzędzi przy użyciu konstruktora [CToolBarCtrl](reference/ctoolbarctrl-class.md).

Każda z tych metod zapewnia dostęp do funkcji składowych formantu paska narzędzi. Po wywołaniu `CToolBar::GetToolBarCtrl` , zwraca odwołanie do `CToolBarCtrl` obiektu, aby można było użyć dowolnego zestawu funkcji Członkowskich. Zobacz [CToolBar](reference/ctoolbar-class.md) , aby uzyskać informacje dotyczące konstruowania i tworzenia paska narzędzi przy użyciu `CToolBar` .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CToolBarCtrl](using-ctoolbarctrl.md)<br/>
[Formanty](controls-mfc.md)
