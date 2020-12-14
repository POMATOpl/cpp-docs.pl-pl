---
description: 'Dowiedz się więcej na temat: przegląd Stanów elementu kontrolki drzewa'
title: Przegląd stanów elementu formantu drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: bfc8f7783fdaafcb66e29040a316028d96bd86c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264027"
---
# <a name="tree-control-item-states-overview"></a>Przegląd stanów elementu formantu drzewa

Każdy element w kontrolce drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) ma bieżący stan. Na przykład element może być wybrany, wyłączony, rozwinięty i tak dalej. W większości, formant drzewa automatycznie ustawia stan elementu, aby odzwierciedlić akcje użytkownika, takie jak zaznaczenie elementu. Jednak można również ustawić stan elementu przy użyciu funkcji składowej [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) i pobrać bieżący stan elementu przy użyciu funkcji składowej [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) . Aby zapoznać się z pełną listą Stanów elementów, zobacz elementy [kontrolne widoku drzewa](/windows/win32/Controls/tree-view-control-item-states) w Windows SDK.

Bieżący stan elementu jest określony przez parametr *nInformacje* . Kontrolka drzewa może zmienić stan elementu, aby odzwierciedlić akcję użytkownika, taką jak zaznaczenie elementu lub ustawienie fokusu w elemencie. Ponadto aplikacja może zmienić stan elementu, aby wyłączyć lub ukryć element lub określić obraz nakładki lub obraz stanu.

W przypadku określenia lub zmiany stanu elementu parametr *nStateMask* określa, które bity stanu należy ustawić, a parametr *nInformacje* zawiera nowe wartości dla tych bitów. Na przykład poniższy przykład zmienia bieżący stan elementu nadrzędnego (określony przez *hParentItem*) w `CTreeCtrl` obiekcie ( `m_treeCtrl` ) na `TVIS_EXPANDPARTIAL` :

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

Innym przykładem zmiany stanu jest ustawienie obrazu nakładki elementu. Aby to osiągnąć, *nStateMask* musi zawierać `TVIS_OVERLAYMASK` wartość, a *nInformacje* musi zawierać indeks jednego z obrazów nakładki przesunięty w lewo o osiem bitów przy użyciu makra [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) . Indeks może mieć wartość 0, aby określić brak obrazu nakładki. Obraz nakładki należy dodać do listy obrazów nakładki kontrolki drzewa przez poprzednie wywołanie funkcji [Korzystanie CImageList:: SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) . Funkcja Określa indeks obrazu, który ma zostać dodany. jest to indeks używany z makrem INDEXTOOVERLAYMASK. Kontrolka drzewa może mieć do czterech obrazów nakładki.

Aby ustawić obraz stanu elementu, *nStateMask* musi zawierać `TVIS_STATEIMAGEMASK` wartość, a *nInformacje* musi zawierać jeden indeks obrazu stanu przesunięty w lewo o 12 bitów przy użyciu makra [INDEXTOSTATEIMAGEMASK](/windows/win32/api/commctrl/nf-commctrl-indextostateimagemask) . Indeks może mieć wartość 0, aby określić brak obrazu stanu. Aby uzyskać więcej informacji na temat nakładania i obrazów stanu, zobacz [listy obrazów kontrolki drzewa](../mfc/tree-control-image-lists.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
