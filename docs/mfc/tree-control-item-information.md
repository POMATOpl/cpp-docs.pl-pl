---
description: 'Dowiedz się więcej na temat: informacje o elementach kontrolki drzewa'
title: Informacje o elementach kontrolki drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
ms.openlocfilehash: ced75bdf6ed6a10e3a34536adf4af0ed1c7e0c86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264144"
---
# <a name="tree-control-item-information"></a>Informacje o elementach kontrolki drzewa

Kontrolki drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) zawierają wiele funkcji Członkowskich, które pobierają informacje o elementach formantu. Funkcja członkowska [GetItem](../mfc/reference/ctreectrl-class.md#getitem) pobiera niektóre lub wszystkie dane skojarzone z elementem. Te dane mogą obejmować tekst, stan, obrazy, liczbę elementów podrzędnych i zdefiniowaną przez aplikację 32-bitową wartość danych. Istnieje również funkcja [SetItem](../mfc/reference/ctreectrl-class.md#setitem) , która może ustawić niektóre lub wszystkie dane skojarzone z elementem.

Funkcje członkowskie [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [getItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata)i [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) pobierają pojedyncze atrybuty elementu. Każda z tych funkcji ma odpowiednią funkcję Set do ustawiania atrybutów elementu.

Funkcja członkowska [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) Pobiera element kontrolki drzewa, który nosi określoną relację do bieżącego elementu. Ta funkcja umożliwia pobranie elementu nadrzędnego, następnego lub poprzedniego widocznego elementu, pierwszego elementu podrzędnego i tak dalej. Istnieją również funkcje członkowskie, które przechodzą przez drzewo: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem)i [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).

Funkcja członkowska [GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) pobiera prostokąt powiązany dla elementu kontrolki drzewa. Funkcje elementów członkowskich [GetCount](../mfc/reference/ctreectrl-class.md#getcount) i [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) pobierają liczbę elementów w kontrolce drzewa oraz liczbę elementów, które są obecnie widoczne w oknie formantu drzewa. Można upewnić się, że określony element jest widoczny, wywołując funkcję elementu członkowskiego [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
