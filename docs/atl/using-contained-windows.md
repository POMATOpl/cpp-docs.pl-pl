---
description: 'Dowiedz się więcej o programie: korzystanie z okien zawartych'
title: Korzystanie z okien zawartych
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 11beb998365a10a8126e37ecbf7388ec6177e659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138219"
---
# <a name="using-contained-windows"></a>Korzystanie z okien zawartych

Biblioteki ATL implementują okna z [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Zawarte okno reprezentuje okno, które deleguje jego komunikaty do obiektu kontenera zamiast obsłużyć je we własnej klasie.

> [!NOTE]
> Nie ma potrzeby wyprowadzania klasy z programu, `CContainedWindowT` Aby można było korzystać z zawartych w nim okien.

W zawartych oknach można albo nadklasować istniejącą klasę systemu Windows lub podklasę istniejącego okna. Aby utworzyć okno, które pełni klasy istniejącej klasy systemu Windows, najpierw określ istniejącą nazwę klasy w konstruktorze dla `CContainedWindowT` obiektu. Następnie Wywołaj `CContainedWindowT::Create` . W celu utworzenia podklasy istniejącego okna nie trzeba określać nazwy klasy systemu Windows (Przekaż wartość NULL do konstruktora). Po prostu wywołaj `CContainedWindowT::SubclassWindow` metodę z uchwytem do okna podklasy.

Zazwyczaj używa się zawartych systemu Windows jako elementów członkowskich danych klasy kontenera. Kontener nie musi być oknem; jednak musi on pochodzić od [CMessageMap](../atl/reference/cmessagemap-class.md).

W zawartym oknie można używać alternatywnych map komunikatów do obsługi komunikatów. Jeśli masz więcej niż jedno okno zawarte, należy zadeklarować kilka alternatywnych map komunikatów, z których każdy odpowiada osobnego okna zawartego.

## <a name="example"></a>Przykład

Poniżej znajduje się przykład klasy kontenera z dwoma zawartymi w nim oknami:

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

Aby uzyskać więcej informacji na temat zawartych okien, zobacz przykład [SubEdit](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) .

## <a name="see-also"></a>Zobacz też

[Klasy okien](../atl/atl-window-classes.md)
