---
description: 'Dowiedz się więcej na temat: jak korzystać z Message-Map odsyłaczy'
title: 'Porady: używanie odsyłacza mapy komunikatów'
ms.date: 11/04/2016
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
ms.openlocfilehash: 4bbc140db59a7df4abd42fdcf68b47273ec3e846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219658"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Porady: używanie odsyłacza mapy komunikatów

W pozycjach z etykietą \<memberFxn> napisz własną funkcję członkowską dla pochodnej klasy [CWnd](../../mfc/reference/cwnd-class.md) . Nadaj swojej funkcji dowolną nazwę. Inne funkcje, takie jak `OnActivate` , są funkcjami składowymi klasy `CWnd` . Jeśli zostanie wywołana, przekaże komunikat do `DefWindowProc` funkcji systemu Windows. Aby przetwarzać komunikaty powiadomień systemu Windows, Zastąp odpowiednią `CWnd` funkcję w klasie pochodnej. Funkcja powinna wywołać przesłoniętą funkcję w klasie bazowej, aby umożliwić klasie podstawowej i systemowi Windows odpowiadanie na wiadomość.

We wszystkich przypadkach należy umieścić prototyp funkcji w `CWnd` nagłówku klasy pochodnej i kod wpisu mapy wiadomości, jak pokazano.

Używane są następujące terminy:

|Okres|Definicja|
|----------|----------------|
|identyfikator|Każdy zdefiniowany przez użytkownika identyfikator elementu menu (komunikaty WM_COMMAND) lub identyfikator formantu (komunikaty powiadomień okna podrzędnego).|
|"Message" i "Włącz wNotifyCode"|Identyfikatory komunikatów systemu Windows zgodnie z definicją w systemie WINDOWS. H.|
|nMessageVariable|Nazwa zmiennej, która zawiera wartość zwracaną z `RegisterWindowMessage` funkcji systemu Windows.|

## <a name="see-also"></a>Zobacz też

[Mapy komunikatów](../../mfc/reference/message-maps-mfc.md)
