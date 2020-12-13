---
description: 'Dowiedz się więcej o programie: podwójne interfejsy i zdarzenia'
title: Podwójne interfejsy i zdarzenia
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 231df7a0dfc8376acd6a9a0f9d85d0ed68fdd0b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153030"
---
# <a name="dual-interfaces-and-events"></a>Podwójne interfejsy i zdarzenia

Chociaż można zaprojektować interfejs zdarzeń jako podwójny, istnieje wiele dobrych przyczyn projektowania. Podstawowym powodem jest to, że źródło zdarzenia będzie wyzwalać zdarzenie tylko za pośrednictwem tabeli metod wirtualnych lub za pośrednictwem `Invoke` , nie obu. Jeśli źródło zdarzenia wyzwala zdarzenie jako bezpośrednie wywołanie metody tablice metod, `IDispatch` metody nigdy nie będą używane i jest jasne, że interfejs powinien być czystym interfejsem tablicowym. Jeśli źródło zdarzenia wyzwala zdarzenie jako wywołanie `Invoke` , metody tablic wirtualnych nigdy nie będą używane i jest jasne, że interfejs powinien być dispinterface. Jeśli określisz interfejsy zdarzeń jako podwójne, będziesz wymagać od klientów zaimplementowania części interfejsu, która nigdy nie będzie używana.

> [!NOTE]
> Ten argument nie ma zastosowania do podwójnych interfejsów, ogólnie. W perspektywie implementacji podwójne są szybkie, wygodne i dobrze obsługiwane sposoby implementowania interfejsów, które są dostępne dla szerokiego zakresu klientów.

Istnieją inne powody, aby uniknąć podwójnych interfejsów zdarzeń; nie Visual Basic ani nie obsługują programu Internet Explorer.

## <a name="see-also"></a>Zobacz też

[Podwójne interfejsy i ATL](../atl/dual-interfaces-and-atl.md)
