---
description: Dowiedz się więcej na temat operacji przesyłania strumieniowego w formantach edycji wzbogaconej
title: Operacje strumieniowe w formantach edycji wzbogaconej
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
ms.openlocfilehash: 3f9dcfb837d9a4f26454a597507712293d3d895c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216486"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Operacje strumieniowe w formantach edycji wzbogaconej

Strumienie służą do transferowania danych do lub z kontrolki edycji wzbogaconej ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Strumień jest zdefiniowany przez strukturę [EDITSTREAM](/windows/win32/api/richedit/ns-richedit-editstream) , która określa bufor i funkcję wywołania zwrotnego zdefiniowanego przez aplikację.

Aby odczytać dane do kontrolki edycji wzbogaconej (czyli strumieniowego przesyłania danych w programie), użyj funkcji elementu członkowskiego [strumienia](../mfc/reference/cricheditctrl-class.md#streamin) . Kontrolka wielokrotnie wywołuje funkcję wywołania zwrotnego zdefiniowaną przez aplikację, która przenosi część danych do bufora za każdym razem.

Aby zapisać zawartość kontrolki edycji wzbogaconej (czyli strumieniowego przesyłania danych), można użyć funkcji składowej [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) . Kontrolka wielokrotnie zapisuje dane w buforze, a następnie wywołuje funkcję wywołania zwrotnego zdefiniowanego przez aplikację. Dla każdego wywołania funkcja wywołania zwrotnego zapisuje zawartość bufora.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
