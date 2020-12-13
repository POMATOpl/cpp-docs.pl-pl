---
description: 'Dowiedz się więcej na temat: korzystanie z IDispEventSimpleImpl'
title: Korzystanie z IDispEventSimpleImpl (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: c0b3f6a0ecdcaae084d3f5d62c19745ee15ac6e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138167"
---
# <a name="using-idispeventsimpleimpl"></a>Korzystanie z interfejsu IDispEventSimpleImpl

W przypadku korzystania `IDispEventSimpleImpl` z programu do obsługi zdarzeń należy:

- Utwórz klasę z [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).

- Dodaj mapę ujścia zdarzeń do swojej klasy.

- Zdefiniuj struktury [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) opisujące zdarzenia.

- Dodaj wpisy do mapy ujścia zdarzeń przy użyciu makra [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) .

- Zaimplementuj metody, które chcesz obsłużyć.

- Doradzanie i dedoradzanie źródła zdarzeń.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak obsłużyć `DocumentChange` zdarzenie wywoływane przez obiekt **aplikacji** programu Word. To zdarzenie jest definiowane jako metoda w `ApplicationEvents` dispinterface.

Przykład pochodzi z [próbki ATLEventHandling](../overview/visual-cpp-samples.md).

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

Ten przykład używa `#import` do generowania wymaganych plików nagłówkowych z biblioteki typów programu Word. Jeśli chcesz użyć tego przykładu z innymi wersjami programu Word, musisz określić właściwy plik DLL Mso. Na przykład pakiet Office 2000 zawiera mso9.dll a OfficeXP zapewnia mso.dll. Ten kod jest uproszczony z *PCH. h* (*stdafx. h* w Visual Studio 2017 i starszych):

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

Jedyne informacje z biblioteki typów rzeczywiście używane w tym przykładzie są identyfikatorem CLSID obiektu programu Word `Application` i identyfikatorem IID `ApplicationEvents` interfejsu. Te informacje są używane tylko w czasie kompilacji.

Poniższy kod pojawia się w prostej. h. Odpowiedni kod jest zanotowany przez Komentarze:

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

Poniższy kod pochodzi z prostej. cpp:

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>Zobacz też

[Obsługa zdarzeń](../atl/event-handling-and-atl.md)<br/>
[Przykład ATLEventHandling](../overview/visual-cpp-samples.md)
