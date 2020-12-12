---
description: 'Dowiedz się więcej na temat: metody tworzenia paska stanu'
title: Metody tworzenia paska stanu
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: 06ae4002fdffb8ba90964b5ef488d0c115b3a0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203058"
---
# <a name="methods-of-creating-a-status-bar"></a>Metody tworzenia paska stanu

MFC udostępnia dwie klasy do tworzenia pasków stanu: [CStatusBar](reference/cstatusbar-class.md) i [CStatusBarCtrl](reference/cstatusbarctrl-class.md) (które zawijają interfejs API usługi Common Control systemu Windows). `CStatusBar` oferuje wszystkie funkcje typowej kontrolki pasek stanu, która automatycznie współdziała z menu i paskami narzędzi, a także obsługuje wiele wymaganych wspólnych ustawień i struktur kontrolek. jednak utworzony plik wykonywalny zwykle będzie większy niż ten, który został utworzony za pomocą programu `CStatusBarCtrl` .

`CStatusBarCtrl` zwykle wynikiem jest mniejszy plik wykonywalny i warto użyć, `CStatusBarCtrl` Jeśli nie zamierzasz zintegrować paska stanu z architekturą MFC. Jeśli planujesz użyć `CStatusBarCtrl` i zintegrować pasek stanu z architekturą MFC, musisz zadbać o to, aby przekazywać manipulowanie formantami paska stanu do MFC. Ta komunikacja nie jest trudna. Jednak w przypadku korzystania z programu jest to dodatkowa niepotrzebna `CStatusBar` .

Visual C++ zapewnia dwa sposoby skorzystania z zalet typowej kontroli nad paskiem stanu.

- Utwórz pasek stanu za pomocą polecenia `CStatusBar` , a następnie Wywołaj [CStatusBar:: GetStatusBarCtrl](reference/cstatusbar-class.md#getstatusbarctrl) , aby uzyskać dostęp do `CStatusBarCtrl` funkcji składowych.

- Utwórz pasek stanu przy użyciu konstruktora [CStatusBarCtrl](reference/cstatusbarctrl-class.md).

Każda z tych metod zapewni dostęp do funkcji Członkowskich kontrolki pasek stanu. Po wywołaniu `CStatusBar::GetStatusBarCtrl` , zwraca odwołanie do `CStatusBarCtrl` obiektu, aby można było użyć dowolnego zestawu funkcji Członkowskich. Zobacz [CStatusBar](reference/cstatusbar-class.md) , aby uzyskać informacje dotyczące konstruowania i tworzenia paska stanu przy użyciu `CStatusBar` .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CStatusBarCtrl](using-cstatusbarctrl.md)<br/>
[Formanty](controls-mfc.md)
