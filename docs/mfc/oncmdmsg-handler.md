---
description: 'Dowiedz się więcej o: procedura obsługi OnCmdMsg'
title: Program obsługi OnCmdMsg
ms.date: 11/04/2016
f1_keywords:
- OnCmdMsg
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
ms.openlocfilehash: 69dfbd7ccc52a6d90b57ef9cedf0f896d65057b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243968"
---
# <a name="oncmdmsg-handler"></a>Program obsługi OnCmdMsg

Aby wykonać routing poleceń, każdy element docelowy polecenia wywołuje `OnCmdMsg` funkcję elementu członkowskiego następnego polecenia docelowego w sekwencji. Elementy docelowe polecenia używane `OnCmdMsg` do określenia, czy mogą obsługiwać polecenie i kierować je do innego obiektu docelowego polecenia, jeśli nie mogą go obsłużyć.

Każda Klasa Target polecenia może przesłonić `OnCmdMsg` funkcję członkowską. Zastąpienia umożliwiają każdej klasie kierowanie poleceń do określonego następnego celu. Okno ramek, na przykład, zawsze kieruje polecenia do jego bieżącego okna podrzędnego lub widoku, jak pokazano w [standardowym marszrucie polecenia](command-routing.md)tabeli.

Domyślna `CCmdTarget` Implementacja programu `OnCmdMsg` używa mapy komunikatów klasy Target polecenia, aby wyszukać funkcję procedury obsługi dla każdego komunikatu polecenia, który odbiera, w taki sam sposób, w jaki przeszukiwane są standardowe komunikaty. Jeśli znajdzie dopasowanie, wywoła procedurę obsługi. Wyszukiwanie w mapie komunikatów zostało wyjaśnione w [sposób, w jaki struktura przeszukuje mapy komunikatów](how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>Zobacz też

[Jak struktura wywołuje program obsługi](how-the-framework-calls-a-handler.md)
