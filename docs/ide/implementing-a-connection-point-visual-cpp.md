---
description: 'Dowiedz się więcej o: implementowanie punktu połączenia'
title: Implementowanie punktu połączenia
ms.date: 05/14/2019
helpviewer_keywords:
- connection points [C++], implementing
- implement connection point wizard [C++]
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
ms.openlocfilehash: bee04d28036ca5a2dfb0f4913adf39f1fdcca565
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281161"
---
# <a name="implement-a-connection-point"></a>Implementowanie punktu połączenia

Aby zaimplementować punkt połączenia za pomocą Kreatora implementacji punktu połączenia, należy utworzyć projekt jako aplikację ATL COM lub jako aplikację MFC, która zawiera obsługę ATL. Możesz użyć [Kreatora projektu ATL](../atl/reference/atl-project-wizard.md) do utworzenia aplikacji ATL lub [dodać obiekt ATL do aplikacji MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) w celu zaimplementowania obsługi ATL dla aplikacji MFC.

> [!NOTE]
> Aby uzyskać informacje na temat implementowania punktów połączenia dla projektu MFC, zobacz [punkty połączenia](../mfc/connection-points.md).

Po utworzeniu projektu w celu zaimplementowania punktu połączenia należy najpierw dodać obiekt ATL. Zobacz [Dodawanie obiektów i kontrolek do projektu ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) , aby wyświetlić listę kreatorów, które dodają obiekty do projektu ATL.

> [!NOTE]
> Kreator nie obsługuje okien dialogowych ATL, usług sieci Web XML utworzonych przy użyciu serwera ATL, obiektów wydajności ani liczników wydajności.

Obiekt połączony (czyli Źródło) może pokazać punkt połączenia dla każdego z jego interfejsów wychodzących. Każdy interfejs wychodzący może być zaimplementowany przez klienta na obiekcie (czyli ujścia). Aby uzyskać więcej informacji, zobacz [punkty połączenia ATL](../atl/atl-connection-points.md).

**Aby zaimplementować punkt połączenia:**

1. W Widok klasy kliknij prawym przyciskiem myszy nazwę klasy dla obiektu ATL.

1. Wybierz polecenie **Dodaj** z menu skrótów, a następnie wybierz polecenie **Dodaj punkt połączenia** , aby wyświetlić [Kreatora implementowania punktu połączenia](#implement-connection-point-wizard).

1. Wybierz interfejsy punktu połączenia do wdrożenia z odpowiednich bibliotek typów i wybierz pozycję **Zakończ**.

1. W Widok klasy zapoznaj się z klasami proxy utworzonymi dla każdego punktu połączenia. Klasy są wyświetlane jako CProxy *InterfaceName* \<T> i pochodzą z [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md).

1. Kliknij dwukrotnie klasę punktu połączenia, aby wyświetlić definicję klasy punktu połączenia.

   - W przypadku zaimplementowania punktu połączenia dla interfejsu własnego projektu zostanie wyświetlona następująca definicja:

     ```cpp
     template< class T >
     class CProxyInterfaceName :
     public IConnectionPointImpl< T, &IID_InterfaceName >
     {
     public:
     };
     ```

   - W przypadku zaimplementowania interfejsu lokalnego metody i właściwości są wyświetlane w treści klasy.

   - W przypadku zaimplementowania punktu połączenia dla innego interfejsu definicja obejmuje metody interfejsu, z których każda poprzedza `Fire_` .

## <a name="in-this-section"></a>W tej sekcji

- [Kreator implementacji punktu połączenia](#implement-connection-point-wizard)

## <a name="implement-connection-point-wizard"></a>Kreator implementacji punktu połączenia

Ten Kreator implementuje punkt połączenia dla obiektu COM. Obiekt połączony (czyli Źródło) może pokazać punkt połączenia dla własnych interfejsów lub dla dowolnego interfejsu wychodzącego. MSVC i Windows udostępniają biblioteki typów, które mają interfejsy wychodzące. Każdy interfejs wychodzący może być zaimplementowany przez klienta na obiekcie (czyli ujścia).

Aby uzyskać więcej informacji, zobacz [punkty połączenia ATL](../atl/atl-connection-points.md).

- **Dostępne biblioteki typów**

  Wyświetla dostępne biblioteki typów, w których znajdują się definicje interfejsów, dla których można zaimplementować punkty połączenia. Wybierz przycisk wielokropka, aby zlokalizować plik, który ma bibliotekę typów do użycia.

- **Lokalizacja**

  Wyświetla lokalizację biblioteki typów aktualnie zaznaczonej na liście **dostępne biblioteki typów** .

- **Interfejsy**

  Wyświetla interfejsy, których definicje są przechowywane w bibliotece typów aktualnie zaznaczonej w polu **dostępne biblioteki typów** .

  |Przycisk transferu|Opis|
  |---------------------|-----------------|
  |**>**|Dodaje do listy **Implementuj punkty połączenia** nazwę interfejsu aktualnie wybraną na liście **interfejsy** .|
  |**>>**|Dodaje do listy **Implementuj punkty połączenia** listę wszystkich nazw interfejsów dostępnych na liście **interfejsy** .|
  |**\<**|Usuwa nazwę interfejsu aktualnie wybraną z listy **Implementuj punkty połączenia** .|
  |**\<\<**|Usuwa wszystkie nazwy interfejsów aktualnie wymienione na liście **Implementuj punkty połączenia** .|

- **Implementowanie punktów połączenia**

  Wyświetla nazwy interfejsów, dla których są implementowane punkty połączenia po wybraniu **przycisku Zakończ**.
