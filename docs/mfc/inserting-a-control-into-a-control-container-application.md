---
description: 'Dowiedz się więcej: kontenery kontrolek ActiveX: Wstawianie kontrolki do aplikacji kontenera kontrolek'
title: 'Kontenery kontrolek ActiveX: wstawianie kontrolki do aplikacji kontenera kontrolek'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 14e1895c39aeea788ab83b8a18be6d8b0ef6c20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220607"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Kontenery kontrolek ActiveX: wstawianie kontrolki do aplikacji kontenera kontrolek

Aby można było uzyskać dostęp do kontrolki ActiveX z aplikacji kontenera kontrolek ActiveX, należy dodać formant ActiveX do aplikacji kontenera za pomocą okna dialogowego [Wstawianie kontrolki ActiveX](../windows/adding-editing-or-deleting-controls.md) .

Aby dodać kontrolkę ActiveX do projektu kontenera kontrolek ActiveX, zobacz [Wyświetlanie i Dodawanie kontrolek ActiveX do okna dialogowego](../windows/adding-editing-or-deleting-controls.md).

Po dodaniu kontrolki należy dodać zmienną członkowską (typ kontrolki ActiveX) do klasy okna dialogowego. Aby uzyskać więcej informacji na temat tej procedury, zobacz [Dodawanie zmiennej składowej](../ide/adding-a-member-variable-visual-cpp.md).

Po dodaniu zmiennej składowej Klasa, nazywana klasą otoki, jest automatycznie generowana i dodawana do projektu. Ta klasa jest używana jako interfejs między kontenerem formantów i osadzonym formantem.

## <a name="see-also"></a>Zobacz też

[Kontenery kontrolek ActiveX](activex-control-containers.md)
