---
description: 'Dowiedz się więcej: porządkowanie elementów w formancie nagłówka'
title: Określanie kolejności elementów w formancie nagłówka
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: 6f6db7b134121c4084d9406ad537bf0ce5dc12cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330116"
---
# <a name="ordering-items-in-the-header-control"></a>Określanie kolejności elementów w formancie nagłówka

Po [dodaniu elementów do kontrolki nagłówka](adding-items-to-the-header-control.md)można manipulować lub uzyskać informacje o ich kolejności przy użyciu następujących funkcji:

- [CHeaderCtrl:: GetOrderArray](reference/cheaderctrl-class.md#getorderarray) i [CHeaderCtrl:: SetOrderArray](reference/cheaderctrl-class.md#setorderarray)

   Pobiera i ustawia kolejność elementów nagłówka od lewej do prawej.

- [CHeaderCtrl:: OrderToIndex](reference/cheaderctrl-class.md#ordertoindex).

   Pobiera wartość indeksu dla określonego elementu nagłówka.

Oprócz poprzednich funkcji Członkowskich styl HDS_DRAGDROP umożliwia użytkownikowi przeciąganie i upuszczanie elementów nagłówka w formancie nagłówka. Aby uzyskać więcej informacji, zobacz [zapewnianie obsługi przeciągania i upuszczania w przypadku elementów nagłówka](providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHeaderCtrl](using-cheaderctrl.md)
