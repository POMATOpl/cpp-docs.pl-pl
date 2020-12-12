---
description: 'Dowiedz się więcej na temat: Dodawanie punktów połączenia do obiektu'
title: Dodawanie punktów połączenia do obiektu
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
ms.openlocfilehash: 7d8274ab37cef28a58666852aad24db7d945d26e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166242"
---
# <a name="adding-connection-points-to-an-object"></a>Dodawanie punktów połączenia do obiektu

W [samouczku ATL](../atl/active-template-library-atl-tutorial.md) przedstawiono sposób tworzenia kontrolki z obsługą punktów połączenia, sposobu dodawania zdarzeń, a następnie implementowania punktu połączenia. ATL implementuje punkty połączenia z klasą [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) .

Do zaimplementowania punktu połączenia dostępne są dwie opcje:

- Zaimplementuj własne, wychodzące źródło zdarzeń, dodając punkt połączenia do formantu lub obiektu.

- Użyj ponownie interfejsu punktu połączenia zdefiniowanego w innej bibliotece typów.

W obu przypadkach Kreator implementacji punktu połączenia używa biblioteki typów, aby wykonać swoją pracę.

### <a name="to-add-a-connection-point-to-a-control-or-object"></a>Aby dodać punkt połączenia do kontrolki lub obiektu

1. Zdefiniuj dispinterface w bloku biblioteki pliku IDL. Jeśli włączono obsługę punktów połączenia podczas tworzenia kontrolki za pomocą Kreatora kontrolki ATL, dispinterface zostanie już utworzony. Jeśli nie włączono obsługi punktów połączenia podczas tworzenia kontrolki, należy ręcznie dodać dispinterface do pliku. idl. Poniżej znajduje się przykład dispinterface. Interfejsy wychodzące nie muszą być interfejsami wysyłania, ale wiele języków skryptów, takich jak VBScript i JScript, wymaga tego, więc w tym przykładzie zastosowano dwa dispinterfaces:

   [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]

   Użyj narzędzia uuidgen.exe lub guidgen.exe do wygenerowania identyfikatora GUID.

2. Dodaj dispinterface jako `[default,source]` interfejs w klasie coclass dla obiektu w pliku. idl projektu. Ponownie, jeśli włączono obsługę punktów połączenia podczas tworzenia kontrolki, Kreator kontrolki ATL utworzy `[default,source` wpis]. Aby ręcznie dodać ten wpis, należy dodać wiersz pogrubiony:

   [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]

   Zapoznaj się z plikiem. idl w przykładowym [cyklem](../overview/visual-cpp-samples.md) ATL.

3. Użyj Widok klasy, aby dodać metody i właściwości do interfejsu zdarzenia. Kliknij prawym przyciskiem myszy klasę w Widok klasy, wskaż polecenie **Dodaj** w menu skrótów, a następnie kliknij polecenie **Dodaj punkt połączenia**.

4. W polu listy **interfejsy źródłowe** kreatora Implementuj punkt połączenia wybierz **interfejsy projektu**. Jeśli wybierzesz interfejs dla kontrolki i naciśniesz przycisk **OK**, będziesz:

   - Wygeneruj plik nagłówka z klasą proxy zdarzeń, która implementuje kod, który spowoduje wychodzące wywołania dla zdarzenia.

   - Dodaj wpis do mapy punktu połączenia.

   Zostanie również wyświetlona lista wszystkich bibliotek typów na komputerze. W celu zdefiniowania tego samego interfejsu wychodzącego w innej bibliotece typów należy używać tylko jednej z tych innych bibliotek typów.

### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>Aby ponownie użyć interfejsu punktu połączenia zdefiniowanego w innej bibliotece typów

1. W Widok klasy kliknij prawym przyciskiem myszy klasę, która implementuje makro **BEGIN_COM_MAP** , wskaż polecenie **Dodaj** w menu skrótów, a następnie kliknij polecenie **Dodaj punkt połączenia**.

2. W Kreatorze Implementuj punkt połączenia wybierz bibliotekę typów i interfejs w bibliotece typów, a następnie kliknij przycisk **Dodaj**.

3. Edytuj plik. idl w:

   - Skopiuj dispinterface z pliku IDL dla obiektu, którego Źródło zdarzenia jest używane.

   - Użyj instrukcji **importlib** w tej bibliotece typów.

## <a name="see-also"></a>Zobacz też

[Punkt połączenia](../atl/atl-connection-points.md)
