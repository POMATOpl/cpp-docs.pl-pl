---
title: Programy obsługi pól listy
ms.date: 11/04/2016
f1_keywords:
- ON_LBN_DBLCLK
- ON_LBN_ERRSPACE
- ON_LBN_SETFOCUS
- ON_LBN_SELCHANGE
- ON_LBN_KILLFOCUS
helpviewer_keywords:
- list boxes [MFC], list box handlers
- ON_LBN_KILLFOCUS
- ON_LBN_ERRSPACE
- ON_LBN_SELCHANGE
- ON_LBN_SETFOCUS
- ON_LBN_DBLCLK
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
ms.openlocfilehash: fc126e1bd26da00608bbb7f1239999ca20eb1727
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637661"
---
# <a name="list-box-handlers"></a>Programy obsługi pól listy

Następujące wpisy mapy mają odpowiednie prototypu funkcji.

|Wpis mapy|Prototyp funkcji|
|---------------|------------------------|
|ON_LBN_DBLCLK ( \<id >, \<memberFxn >)|() void memberFxn afx_msg;|
|ON_LBN_ERRSPACE ( \<id >, \<memberFxn >)|() void memberFxn afx_msg;|
|ON_LBN_KILLFOCUS ( \<id >, \<memberFxn >)|() void memberFxn afx_msg;|
|ON_LBN_SELCHANGE ( \<id >, \<memberFxn >)|() void memberFxn afx_msg;|
|ON_LBN_SETFOCUS ( \<id >, \<memberFxn >)|() void memberFxn afx_msg;|

## <a name="see-also"></a>Zobacz też

[Mapy komunikatów](../../mfc/reference/message-maps-mfc.md)

