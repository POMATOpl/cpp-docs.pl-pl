---
description: 'Dowiedz się więcej na temat: CTreeCtrl a CTreeView'
title: CTreeCtrl a CTreeView
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: edaf2662d483a23c7618a143ee4aabe7910cf121
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309423"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl a CTreeView

MFC udostępnia dwie klasy, które hermetyzują formanty drzewa: [CTreeCtrl](reference/ctreectrl-class.md) i [CTreeView](reference/ctreeview-class.md). Każda klasa jest przydatna w różnych sytuacjach.

Użyj `CTreeCtrl` , gdy potrzebujesz prostej kontrolki okna podrzędnego, na przykład w oknie dialogowym. Jest to szczególnie przydatne `CTreeCtrl` , jeśli w oknie są inne kontrolki podrzędne, jak w przypadku typowego okna dialogowego.

Użyj `CTreeView` , gdy chcesz, aby formant drzewa działał jak okno widoku w architekturze dokumentu/widoku, a także jako formant drzewa. Zajmie `CTreeView` cały obszar klienta okna ramki lub okna rozdzielacza. Zostanie automatycznie zmieniony rozmiar po zmianie rozmiaru okna nadrzędnego i może przetwarzać komunikaty poleceń z menu, klawiszy skrótów i pasków narzędzi. Ponieważ kontrolka drzewa zawiera dane niezbędne do wyświetlenia drzewa, odpowiedni obiekt dokumentu nie musi być skomplikowany — można nawet użyć [CDocument](reference/cdocument-class.md) jako typu dokumentu w szablonie dokumentu.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](using-ctreectrl.md)<br/>
[Formanty](controls-mfc.md)
