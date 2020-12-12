---
description: 'Dowiedz się więcej o programie: niszczenie okien ramowych'
title: Niszczenie okien ramowych
ms.date: 11/04/2016
f1_keywords:
- PostNcDestroy
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
ms.openlocfilehash: 192b1b21881f4a9f94a4fb1d6c7b18b4a91ac579
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327858"
---
# <a name="destroying-frame-windows"></a>Niszczenie okien ramowych

Struktura MFC zarządza zniszczeniem okna oraz tworzeniem tych okien skojarzonych z dokumentami i widokami struktury. W przypadku tworzenia dodatkowych okien użytkownik jest odpowiedzialny za ich zniszczenie.

W strukturze, gdy użytkownik zamknie okno ramki, domyślna procedura obsługi [OnClose](reference/cwnd-class.md#onclose) okna wywołuje [DestroyWindow](reference/cwnd-class.md#destroywindow). Ostatnia funkcja członkowska wywoływana, gdy okno systemu Windows jest niszczone to [OnNcDestroy](reference/cwnd-class.md#onncdestroy), która wykonuje pewne oczyszczanie, wywołuje [domyślną](reference/cwnd-class.md#default) funkcję członkowską w celu przeprowadzenia oczyszczania systemu Windows i po raz ostatni wywołuje wirtualną funkcję członkowską [PostNcDestroy](reference/cwnd-class.md#postncdestroy). Implementacja [obiektu CFrameWnd](reference/cframewnd-class.md) `PostNcDestroy` usuwania obiektu okna języka C++. Nigdy nie należy używać operatora C++ **`delete`** w oknie ramek. Zamiast tego użyj polecenia cmdlet `DestroyWindow`.

Gdy okno główne zostanie zamknięte, aplikacja zostanie zamknięta. W przypadku zmodyfikowania niezapisanych dokumentów w strukturze zostanie wyświetlone okno komunikatu z monitem o zapisanie dokumentów i zagwarantowanie, że odpowiednie dokumenty zostały zapisane w razie potrzeby.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Tworzenie okien ramowych dokumentu](creating-document-frame-windows.md)

## <a name="see-also"></a>Zobacz też

[Korzystanie z okien ramowych](using-frame-windows.md)
