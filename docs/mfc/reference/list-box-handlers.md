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
ms.openlocfilehash: a104e6a8b3ed40c65b704738461c083a745464b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322413"
---
# <a name="list-box-handlers"></a>Programy obsługi pól listy

Następujące wpisy mapy mają odpowiednie prototypu funkcji.

|Wpis mapy|Prototyp funkcji|
|---------------|------------------------|
|ON_LBN_DBLCLK( \<id>, \<memberFxn> )|() void memberFxn afx_msg;|
|ON_LBN_ERRSPACE( \<id>, \<memberFxn> )|() void memberFxn afx_msg;|
|ON_LBN_KILLFOCUS( \<id>, \<memberFxn> )|() void memberFxn afx_msg;|
|ON_LBN_SELCHANGE( \<id>, \<memberFxn> )|() void memberFxn afx_msg;|
|ON_LBN_SETFOCUS( \<id>, \<memberFxn> )|() void memberFxn afx_msg;|

## <a name="see-also"></a>Zobacz także

[Mapy komunikatów](../../mfc/reference/message-maps-mfc.md)
