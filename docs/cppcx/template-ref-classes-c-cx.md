---
description: 'Dowiedz się więcej o: klasach ref szablonu (C++/CX)'
title: Klasy odwołania szablonu (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: c8f3e668dddd80a2ce05f10f9a5d2ada30096c3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307629"
---
# <a name="template-ref-classes-ccx"></a>Klasy odwołania szablonu (C++/CX)

Szablony języka C++ nie są publikowane w metadanych i dlatego nie mogą mieć publicznej ani chronionej dostępności w programie. Oczywiście w programie można używać standardowych szablonów języka C++. Ponadto można zdefiniować prywatną klasę ref jako szablon i można zadeklarować jawnie wyspecjalizowaną klasę ref szablonu jako prywatną składową w publicznej klasie referencyjnej.

## <a name="authoring-ref-class-templates"></a>Tworzenie szablonów klas referencyjnych

Poniższy przykład pokazuje sposób deklarowania prywatnej klasy ref jako szablonu, a także sposobu deklarowania standardowego szablonu C++ i sposobu deklarowania ich jako elementów członkowskich w publicznej klasie referencyjnej. Należy pamiętać, że standardowy szablon języka C++ może być wyspecjalizowany dla typu środowisko wykonawcze systemu Windows, w tym przypadku platform:: String ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Zobacz też

[System typów (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Dokumentacja języka C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Dokumentacja przestrzeni nazw](../cppcx/namespaces-reference-c-cx.md)
