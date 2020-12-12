---
description: 'Dowiedz się więcej o: komunikowanie się z kontrolką drzewa'
title: Komunikacja z formantem drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 82ee4fe0beb65e44166b4d68ffd44923b7fe0c76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310567"
---
# <a name="communicating-with-a-tree-control"></a>Komunikacja z formantem drzewa

Używasz różnych metod wywoływania funkcji Członkowskich w obiekcie [CTreeCtrl](reference/ctreectrl-class.md) w zależności od sposobu utworzenia obiektu:

- Jeśli formant drzewa znajduje się w oknie dialogowym, użyj zmiennej składowej typu `CTreeCtrl` , która została utworzona w klasie okna dialogowego.

- Jeśli formant drzewa jest oknem podrzędnym, użyj `CTreeCtrl` obiektu (lub wskaźnika) użytego do konstruowania obiektu.

- Jeśli używasz `CTreeView` obiektu, użyj funkcji [CTreeView:: funkcji GetTreeCtrl](reference/ctreeview-class.md#gettreectrl) , aby pobrać odwołanie do kontrolki drzewa. Możesz zainicjować inne odwołanie z tą wartością lub przypisać adres odwołania do `CTreeCtrl` wskaźnika.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](using-ctreectrl.md)<br/>
[Formanty](controls-mfc.md)
