---
title: Implementowanie okna z CWindowImpl
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: 7ce1a2ec08e49e047aee5248bda0094d9e392614
ms.sourcegitcommit: ced5ff1431ffbd25b20d106901955532723bd188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "92135518"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Implementowanie okna z CWindowImpl

Aby zaimplementować okno, należy utworzyć klasę z `CWindowImpl` . W klasie pochodnej deklaruj mapę komunikatów i funkcje obsługi komunikatów. Teraz można używać klasy na trzy różne sposoby:

- [Utwórz okno na podstawie nowej klasy systemu Windows](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Superklasa istniejącej klasy systemu Windows](#_atl_superclassing_an_existing_windows_class)

- [Podklasa istniejącego okna](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Tworzenie okna na podstawie nowej klasy systemu Windows

`CWindowImpl` zawiera makro [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) , które zadeklaruje informacje o klasie systemu Windows. To makro implementuje `GetWndClassInfo` funkcję, która używa [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) do definiowania informacji o nowej klasie systemu Windows. Gdy `CWindowImpl::Create` jest wywoływana, ta klasa systemu Windows jest zarejestrowana i tworzone jest nowe okno.

> [!NOTE]
> `CWindowImpl` przekazuje wartość NULL do `DECLARE_WND_CLASS` makra, co oznacza, że ATL generuje nazwę klasy systemu Windows. Aby określić własną nazwę, należy przekazać ciąg do DECLARE_WND_CLASS w `CWindowImpl` klasie pochodnej.

## <a name="example-implement-a-window"></a>Przykład: implementowanie okna

Poniżej znajduje się przykład klasy implementującej okno oparte na nowej klasie systemu Windows:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Aby utworzyć okno, Utwórz wystąpienie elementu, `CMyWindow` a następnie Wywołaj `Create` metodę.

> [!NOTE]
> Aby zastąpić domyślne informacje o klasie systemu Windows, zaimplementuj `GetWndClassInfo` metodę w klasie pochodnej, ustawiając `CWndClassInfo` elementy członkowskie na odpowiednie wartości.

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a> Superklasa istniejącej klasy systemu Windows

Makro [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) umożliwia utworzenie okna z klasą istniejącą klasą systemu Windows. Określ to makro w `CWindowImpl` klasie pochodnej. Podobnie jak w przypadku każdego innego okna ATL, komunikaty są obsługiwane przez mapę komunikatów.

W przypadku korzystania z DECLARE_WND_SUPERCLASS Nowa Klasa systemu Windows zostanie zarejestrowana. Ta nowa klasa będzie taka sama jak istniejąca Klasa określona przez użytkownika, ale zastąpi procedurę okna z `CWindowImpl::WindowProc` (lub funkcją, która zastępuje tę metodę).

## <a name="example-superclass-the-edit-class"></a>Przykład: Superklasa klasy Edit

Poniżej znajduje się przykład klasy, która stanowi Superklasa klasy standardowej edycji:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Aby utworzyć okno edycji z klasą, Utwórz wystąpienie elementu, `CMyEdit` a następnie Wywołaj `Create` metodę.

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a> Podklasa istniejącego okna

Aby utworzyć podklasę istniejącego okna, Utwórz klasę z `CWindowImpl` i Zadeklaruj mapę komunikatów, jak w dwóch powyższych przypadkach. Należy jednak pamiętać, że nie określisz żadnych informacji o klasie systemu Windows, ponieważ zostanie poddana podklasie istniejącym okno.

Zamiast wywoływania `Create` , wywołaj `SubclassWindow` i przekaż go do istniejącego okna, które chcesz utworzyć podklasę. Gdy okno zostanie podklasy, użyje `CWindowImpl::WindowProc` (lub funkcji, która zastępuje tę metodę), aby skierować komunikaty do mapy komunikatów. Aby odłączyć okno z podklasą od obiektu, wywołaj `UnsubclassWindow` . Oryginalna procedura okna zostanie przywrócona.

## <a name="see-also"></a>Zobacz też

[Implementowanie okna](../atl/implementing-a-window.md)
