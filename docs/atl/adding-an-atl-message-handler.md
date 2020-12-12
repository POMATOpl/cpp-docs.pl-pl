---
description: 'Dowiedz się więcej na temat: Dodawanie programu obsługi komunikatów ATL'
title: Dodawanie programu obsługi komunikatów ATL
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
ms.openlocfilehash: 263cbcb863ee287c9b3f4650263a3fac33d7ab7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166346"
---
# <a name="adding-an-atl-message-handler"></a>Dodawanie programu obsługi komunikatów ATL

Aby dodać program obsługi komunikatów (funkcja członkowska, która obsługuje komunikaty systemu Windows) do kontrolki, najpierw wybierz kontrolkę w Widok klasy. Następnie otwórz okno **Właściwości** , wybierz ikonę **komunikaty** , a następnie kliknij kontrolkę listy rozwijanej w polu obok wymaganego komunikatu. Spowoduje to dodanie deklaracji dla programu obsługi komunikatów w pliku nagłówkowym kontrolki i szkieletowej implementacji programu obsługi w pliku. cpp kontrolki. Spowoduje to również dodanie mapy komunikatów i dodanie wpisu do programu obsługi.

Dodawanie programu obsługi komunikatów w ATL jest podobne do dodawania obsługi komunikatów do klasy MFC. Aby uzyskać więcej informacji [, zobacz Dodawanie programu obsługi komunikatów MFC](../mfc/reference/adding-an-mfc-message-handler.md) .

Poniższe warunki dotyczą tylko dodawania obsługi komunikatów ATL:

- Procedury obsługi komunikatów są zgodne z tą samą konwencją nazewnictwa jak MFC.

- Nowe wpisy mapy wiadomości są dodawane do głównej mapy komunikatów. Kreator nie rozpoznaje alternatywnych map i łańcuchów komunikatów.

## <a name="see-also"></a>Zobacz też

[Implementowanie okna](../atl/implementing-a-window.md)
