---
description: 'Dowiedz się więcej na temat: klasy związane z formantami edycji wzbogaconej'
title: Klasy związane z formantami edycji wzbogaconej
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], and CRichEditItem
- CRichEditCtrl class [MFC], related classes
- CRichEditDoc class [MFC], Rich Edit controls
- rich edit controls [MFC], classes related to
- classes [MFC], related to rich edit controls
- rich edit controls [MFC], and CRichEditView
- CRichEditCtrlItem class and CRichEditCtrl
- rich edit controls [MFC], and CRichEditDoc
- CRichEditView class [MFC], and CRichEditCtrl
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
ms.openlocfilehash: b44c5a874c7f48c132f31483bf5ee73eafbe4da5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176681"
---
# <a name="classes-related-to-rich-edit-controls"></a>Klasy związane z formantami edycji wzbogaconej

Klasy [CRichEditView](reference/cricheditview-class.md), [CRichEditDoc](reference/cricheditdoc-class.md)i [CRichEditCntrItem](reference/cricheditcntritem-class.md) zapewniają funkcje kontrolki edycji wzbogaconej ([CRichEditCtrl](reference/cricheditctrl-class.md)) w kontekście architektury dokumentu/widoku MFC. `CRichEditView` Zachowuje cechę tekstu i formatowania tekstu. `CRichEditDoc` zachowuje listę elementów klienta OLE, które znajdują się w widoku. `CRichEditCntrItem` zapewnia dostęp po stronie kontenera do elementu klienta OLE. Aby zmodyfikować zawartość elementu `CRichEditView` , użyj [CRichEditView:: GetRichEditCtrl](reference/cricheditview-class.md#getricheditctrl) w celu uzyskania dostępu do źródłowej kontrolki edycji wzbogaconej.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CRichEditCtrl](using-cricheditctrl.md)<br/>
[Formanty](controls-mfc.md)
