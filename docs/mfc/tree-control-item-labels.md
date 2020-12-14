---
description: 'Dowiedz się więcej o: etykiety elementów kontrolki drzewa'
title: Etykiety elementów formantu drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
ms.openlocfilehash: 62113a7534bf234ac8dde1154d5732bc29df8387
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264074"
---
# <a name="tree-control-item-labels"></a>Etykiety elementów formantu drzewa

Zwykle określasz tekst etykiety elementu podczas dodawania elementu do kontrolki drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). `InsertItem`Funkcja członkowska może przekazać strukturę [TVITEM](/windows/win32/api/commctrl/ns-commctrl-tvitemw) , która definiuje właściwości elementu, w tym ciąg zawierający tekst etykiety. `InsertItem` ma kilka przeciążeń, które można wywoływać przy użyciu różnych kombinacji parametrów.

Kontrolka drzewa przydziela pamięć do przechowywania każdego elementu; tekst etykiet elementów przyjmuje znaczną część tej pamięci. Jeśli aplikacja zachowuje kopię ciągów w kontrolce drzewa, można zmniejszyć wymagania dotyczące pamięci kontrolki, określając **LPSTR_TEXTCALLBACK** wartość w *pszText* `TV_ITEM` lub parametr *lpszItem* , zamiast przekazywać rzeczywiste ciągi do formantu drzewa. Użycie **LPSTR_TEXTCALLBACK** powoduje, że formant drzewa Pobiera tekst etykiety elementu z aplikacji za każdym razem, gdy element wymaga odrysowania. Aby można było pobrać tekst, formant drzewa wysyła [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) komunikat powiadomienia, który zawiera adres struktury [NMTVDISPINFO](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow) . Musisz odpowiedzieć przez ustawienie odpowiednich członków zawartej struktury.

Kontrolka drzewa używa pamięci przydzieloną z sterty procesu, który tworzy formant drzewa. Maksymalna liczba elementów w kontrolce drzewa zależy od ilości dostępnej pamięci w stercie. Każdy element pobiera 64 bajtów.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
