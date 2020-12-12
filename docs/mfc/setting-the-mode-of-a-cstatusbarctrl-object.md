---
description: 'Dowiedz się więcej na temat: Ustawianie trybu obiektu CStatusBarCtrl'
title: Ustawianie trybu obiektu CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: 46a87c17c68059e1d12476f4963f159cd2915824
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217110"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Ustawianie trybu obiektu CStatusBarCtrl

Istnieją dwa tryby dla `CStatusBarCtrl` obiektu: proste i nieproste. W większości przypadków kontrolka pasek stanu będzie zawierać co najmniej jedną część, wraz z tekstem i prawdopodobnie ikoną lub ikonami. Jest to nazywane trybem nieprostym. Aby uzyskać więcej informacji na temat tego trybu, zobacz [Inicjowanie części obiektu CStatusBarCtrl](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Istnieją jednak przypadki, w których wystarczy tylko wyświetlić pojedynczy wiersz tekstu. W takim przypadku tryb prosty jest wystarczający dla Twoich potrzeb. Aby zmienić tryb `CStatusBarCtrl` prostego obiektu, należy wywołać funkcję [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) składowej. Gdy kontrolka pasek stanu jest w trybie prostym, Ustaw tekst, wywołując `SetText` funkcję członkowską, przekazując 255 jako wartość parametru *nPane* .

Można użyć funkcji [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) do określenia trybu, `CStatusBarCtrl` w którym znajduje się obiekt.

> [!NOTE]
> Jeśli obiekt paska stanu jest zmieniany z nieproste na prosta lub na odwrót, okno zostanie natychmiast ponownie narysowane i, w razie potrzeby, wszystkie zdefiniowane części zostaną automatycznie przywrócone.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
