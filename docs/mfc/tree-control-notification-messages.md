---
description: 'Dowiedz się więcej na temat: komunikaty powiadomień dotyczących kontrolki drzewa'
title: Komunikaty powiadomień dotyczących formantu drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: 899b6469a2de9a076dd33e62c5023f502448d45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263988"
---
# <a name="tree-control-notification-messages"></a>Komunikaty powiadomień dotyczących formantu drzewa

Kontrolka drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) wysyła następujące komunikaty powiadomienia jako komunikaty WM_NOTIFY:

|Komunikat z powiadomieniem|Opis|
|--------------------------|-----------------|
|TVN_BEGINDRAG|Sygnalizuje rozpoczęcie operacji przeciągania i upuszczania|
|TVN_BEGINLABELEDIT|Sygnalizuje początek edycji etykiet w miejscu|
|TVN_BEGINRDRAG|Sygnalizuje rozpoczęcie operacji przeciągania i upuszczania przy użyciu prawego przycisku myszy|
|TVN_DELETEITEM|Sygnalizuje usunięcie określonego elementu|
|TVN_ENDLABELEDIT|Sygnalizuje koniec edycji etykiety|
|TVN_GETDISPINFO|Żąda informacji wymaganych przez formant drzewa do wyświetlenia elementu|
|TVN_ITEMEXPANDED|Sygnalizuje, że lista elementów podrzędnych elementu nadrzędnego została rozwinięta lub zwinięta|
|TVN_ITEMEXPANDING|Sygnalizuje, że lista elementów podrzędnych elementu nadrzędnego zostanie rozwinięta lub zwinięty|
|TVN_KEYDOWN|Sygnalizuje zdarzenie klawiatury|
|TVN_SELCHANGED|Sygnalizuje, że zaznaczenie zostało zmienione z jednego elementu na inny|
|TVN_SELCHANGING|Sygnalizuje, że zaznaczenie zostanie zmienione z jednego elementu na inny|
|TVN_SETDISPINFO|Powiadomienie o zaktualizowaniu informacji przechowywanych dla elementu|

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
