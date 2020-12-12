---
description: 'Dowiedz się więcej o programie: sekwencja niszczenia okien'
title: Sekwencja likwidacji okna
ms.date: 11/04/2016
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
ms.openlocfilehash: 2ba60f1dcd3668a754bbe4384a6c8cf6b4d541d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207686"
---
# <a name="window-destruction-sequence"></a>Sekwencja likwidacji okna

W środowisku MFC, gdy użytkownik zamknie okno ramki, domyślny uchwyt [OnClose](../mfc/reference/cwnd-class.md#onclose) okna wywołuje [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ostatnia funkcja członkowska wywoływana, gdy okno systemu Windows jest niszczone to [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), która wykonuje pewne oczyszczanie, wywołuje [domyślną](../mfc/reference/cwnd-class.md#default) funkcję członkowską w celu przeprowadzenia oczyszczania systemu Windows i po raz ostatni wywołuje wirtualną funkcję członkowską [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Implementacja [obiektu CFrameWnd](../mfc/reference/cframewnd-class.md) `PostNcDestroy` usuwania obiektu okna języka C++.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Alokowanie i dealokowanie pamięci okna](../mfc/allocating-and-deallocating-window-memory.md)

- [Odłączanie obiektu CWnd od jego właściwości HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Zobacz też

[Niszczenie obiektów okien](../mfc/destroying-window-objects.md)
