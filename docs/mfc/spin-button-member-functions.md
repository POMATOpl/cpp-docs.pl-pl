---
description: 'Dowiedz się więcej o: funkcjach członkowskich przycisku pokrętła'
title: Funkcje członkowskie przycisku pokrętła
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 6a03ab33d29634ed85d807eb5b51edfdef310d65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216837"
---
# <a name="spin-button-member-functions"></a>Funkcje członkowskie przycisku pokrętła

Istnieje kilka funkcji Członkowskich dostępnych dla formantu pokrętła ([Korzystanie CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Te funkcje umożliwiają zmianę następujących atrybutów przycisku pokrętła.

- **Przyspieszenie** Możesz dostosować szybkość zmiany położenia, gdy użytkownik będzie miał przycisk strzałki w dół. Aby współpracować z przyspieszeniem, użyj funkcji składowych [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) i [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) .

- **Baza** Można zmienić bazę (10 lub 16) używaną do wyświetlania pozycji w podpisie okna partnera. Aby współdziałać z podstawą, użyj funkcji [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) i [setbase](../mfc/reference/cspinbuttonctrl-class.md#setbase) .

- **Okno partnera** Można dynamicznie ustawić okno partnera. Aby zbadać lub zmienić, który formant jest oknem partnera, użyj funkcji elementów członkowskich [getkolega](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) i [setkolega](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) .

- **Pozycja** Można wysyłać zapytania i zmieniać położenie. Aby bezpośrednio współpracować z pozycją, użyj funkcji składowych [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) i [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) . Ponieważ podpis formantu partnera może ulec zmianie (na przykład w przypadku, gdy kolega jest formantem edycji), `GetPos` Pobiera bieżący podpis i odpowiednio dostosowuje położenie.

- **Zakres** Można zmienić maksymalne i minimalne położenia przycisku pokrętła. Domyślnie wartość maksymalna to 0, a wartość minimalna to 100. Ponieważ domyślna wartość maksymalna jest mniejsza niż wartość domyślna minimum, akcje przycisków strzałek są intuicyjne. Zazwyczaj należy ustawić zakres przy użyciu funkcji elementu członkowskiego [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) . Aby zbadać zakres, użyj [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
