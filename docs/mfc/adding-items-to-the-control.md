---
description: 'Dowiedz się więcej na temat: Dodawanie elementów do kontrolki'
title: Dodawanie elementów do formantu
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 44a553564aa9a98806cd8e4d9551c9474421105f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249025"
---
# <a name="adding-items-to-the-control"></a>Dodawanie elementów do formantu

Aby dodać elementy do kontrolki listy ([CListCtrl](reference/clistctrl-class.md)), wywołaj jedną z kilku wersji funkcji składowej [InsertItem](reference/clistctrl-class.md#insertitem) , w zależności od posiadanych informacji. Jedna wersja przyjmuje przygotowaną strukturę [LVITEM](/windows/win32/api/commctrl/ns-commctrl-lvitemw) . Ponieważ `LVITEM` Struktura zawiera wiele elementów członkowskich, masz większą kontrolę nad atrybutami elementu kontrolki listy.

Dwa ważne elementy członkowskie (w odniesieniu do widoku raportu) `LVITEM` struktury są `iItem` elementami i `iSubItem` . `iItem`Składowa jest indeksem (liczonym od zera) elementu, do którego odwołuje się struktura, a `iSubItem` składowa jest indeksem jednego z nich, lub zero, jeśli struktura zawiera informacje o elemencie. Za pomocą tych dwóch elementów członkowskich, które można określić dla każdego elementu, typ i wartość informacji o podelementach, które są wyświetlane, gdy kontrolka listy jest w widoku raportu. Aby uzyskać więcej informacji, zobacz [CListCtrl:: SetItem](reference/clistctrl-class.md#setitem).

Dodatkowe elementy członkowskie określają tekst, ikonę, stan i dane elementu elementu. "Dane elementu" to zdefiniowana przez aplikację wartość skojarzona z elementem widoku listy. Aby uzyskać więcej informacji na temat `LVITEM` struktury, zobacz [CListCtrl:: GetItem](reference/clistctrl-class.md#getitem).

Inne wersje `InsertItem` mają jedną lub więcej oddzielnych wartości, które odpowiadają członkom `LVITEM` struktury, co pozwala na zainicjowanie tylko tych członków, które mają być obsługiwane. Ogólnie rzecz biorąc, kontrolka list zarządza magazynem dla elementów listy, ale zamiast tego można przechowywać niektóre informacje w aplikacji, używając "elementów wywołania zwrotnego". Aby uzyskać więcej informacji, zobacz [elementy wywołania zwrotnego i Maska wywołania zwrotnego](callback-items-and-the-callback-mask.md) w tym temacie oraz [elementy wywołania zwrotnego i Maska wywołania zwrotnego](/windows/win32/Controls/using-list-view-controls) w Windows SDK.

Aby uzyskać więcej informacji, zobacz [dodawanie List-View elementów i podelementów](/windows/win32/Controls/using-list-view-controls).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CListCtrl](using-clistctrl.md)<br/>
[Formanty](controls-mfc.md)
