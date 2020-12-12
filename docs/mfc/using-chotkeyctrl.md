---
description: 'Dowiedz się więcej na temat: korzystanie z CHotKeyCtrl'
title: Korzystanie z CHotKeyCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
ms.openlocfilehash: 7f17063a4fb3732a9b121e2b93f5d55e51d5654a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271684"
---
# <a name="using-chotkeyctrl"></a>Korzystanie z CHotKeyCtrl

Kontrolka klawisza gorąca, reprezentowana przez klasę [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), to okno, w którym jest wyświetlana tekstowa reprezentacja kombinacji klawiszy, na przykład Ctrl + Shift + Q. Utrzymuje również wewnętrzną reprezentację tego klucza w postaci kodu klucza wirtualnego i zestawu flag, które reprezentują stan przesunięcia. Kontrolka klawisza dostępu nie ustawia w rzeczywistości klawisza dostępu do programu. (Aby uzyskać listę standardowych kodów kluczy wirtualnych, zobacz Winuser. h.)

Użyj formantu klawisza dostępu, aby uzyskać dane wejściowe użytkownika, dla którego klucz dostępu ma zostać skojarzony z oknem lub wątkiem. Kontrolki klawisza dostępu są często używane w oknach dialogowych, na przykład podczas monitowania użytkownika o przypisanie klawisza skrótu. Jest on odpowiedzialny za pobieranie wartości opisujących klawisz gorąca z kontrolki klawisza gorąca i wywołanie odpowiednich funkcji w celu skojarzenia klawisza gorąca z oknem lub wątkiem.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Używanie formantu klawisza dostępu](../mfc/using-a-hot-key-control.md)

- [Ustawianie klawisza dostępu](../mfc/setting-a-hot-key.md)

- [Globalne klawisze dostępu](../mfc/global-hot-keys.md)

- [Klawisze dostępu właściwe dla wątków](../mfc/thread-specific-hot-keys.md)

## <a name="see-also"></a>Zobacz też

[Formanty](../mfc/controls-mfc.md)
