---
description: Dowiedz się więcej na temat list obrazów kontrolki drzewa
title: Listy obrazów kontrolki drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
ms.openlocfilehash: ce76cca5642208d4158b36c45c150202270258e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264157"
---
# <a name="tree-control-image-lists"></a>Listy obrazów kontrolki drzewa

Każdy element w kontrolce drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) może mieć skojarzoną parę obrazów mapy bitowej. Obrazy są wyświetlane po lewej stronie etykiety elementu. Po wybraniu elementu jest wyświetlany jeden obraz, a drugi jest wyświetlany, gdy element nie jest zaznaczony. Na przykład element może wyświetlić otwarty folder, gdy jest zaznaczony, i folder zamknięty, gdy nie jest zaznaczony.

Aby można było używać obrazów elementów, należy utworzyć listę obrazów przez utworzenie obiektu [Korzystanie CImageList](../mfc/reference/cimagelist-class.md) i użycie funkcji [Korzystanie CImageList:: Create](../mfc/reference/cimagelist-class.md#create) w celu utworzenia listy skojarzonych obrazów. Następnie Dodaj odpowiednie mapy bitowe do listy, a następnie skojarz listę z kontrolką drzewa przy użyciu funkcji elementu członkowskiego [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) . Domyślnie wszystkie elementy wyświetlają pierwszy obraz na liście obrazów dla Stanów wybranych i niezaznaczonych. Można zmienić zachowanie domyślne dla danego elementu przez określenie indeksów wybranych i niezaznaczonych obrazów podczas dodawania elementu do formantu drzewa przy użyciu funkcji składowej [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) . Indeksy można zmienić po dodaniu elementu przy użyciu funkcji składowej [SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage) .

Listy obrazów kontrolki drzewa mogą również zawierać obrazy nakładane, które są przeznaczone do nakładania się na obrazy elementów. Wartość różna od zera w bitach od 8 do 11 stanu elementu kontrolki drzewa Określa indeks jednego z nich (0 oznacza brak obrazu nakładki). Ze względu na to, że używany jest 4-bitowy indeks, obrazy nakładane muszą pochodzić z pierwszych 15 obrazów na listach obrazów. Aby uzyskać więcej informacji na temat stanów elementów kontrolki drzewa, zobacz [Omówienie Stanów elementu kontrolki drzewa](../mfc/tree-control-item-states-overview.md) wcześniej w tym temacie.

Jeśli określono listę obrazu stanu, formant drzewa rezerwuje miejsce na lewo od ikony każdego elementu obrazu stanu. Aplikacja może używać obrazów stanu, takich jak zaznaczone i wyczyszczone pola wyboru, aby wskazać Stany elementów zdefiniowane przez aplikację. Wartość różna od zera w bitach od 12 do 15 określa jeden indeks obrazu stanu (0 oznacza brak obrazu stanu).

Określając **I_IMAGECALLBACK** wartość zamiast indeksu obrazu, można opóźnić Określanie zaznaczonego lub niewybranego obrazu do momentu odrysowania elementu. **I_IMAGECALLBACK** kieruje formant drzewa do wysyłania zapytań do aplikacji dla indeksu, wysyłając [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) komunikat powiadomienia.

Funkcja elementu członkowskiego [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) pobiera uchwyt listy obrazów kontrolki drzewa. Ta funkcja jest przydatna, jeśli trzeba dodać więcej obrazów do listy. Aby uzyskać więcej informacji na temat list obrazów, zobacz [Używanie korzystanie CImageList](../mfc/using-cimagelist.md), [Korzystanie CImageList](../mfc/reference/cimagelist-class.md) w *Kompendium MFC* oraz [list obrazów](/windows/win32/controls/image-lists) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
