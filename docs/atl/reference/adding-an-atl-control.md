---
description: 'Dowiedz się więcej na temat: Dodawanie formantu ATL'
title: Dodawanie kontrolki ATL
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
ms.openlocfilehash: 91fe393a1e93deb2173ac95a42b7ab9cca339535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165709"
---
# <a name="adding-an-atl-control"></a>Dodawanie kontrolki ATL

Użyj tego kreatora, aby dodać obiekt interfejsu użytkownika do projektu, który obsługuje interfejsy dla wszystkich potencjalnych kontenerów. Aby można było obsługiwać te interfejsy, projekt musi zostać utworzony jako aplikacja ATL lub jako aplikacja MFC, która zawiera obsługę ATL. Możesz użyć [Kreatora projektu ATL](../../atl/reference/atl-project-wizard.md) do utworzenia aplikacji ATL lub [dodać obiekt ATL do aplikacji MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) w celu zaimplementowania obsługi ATL dla aplikacji MFC.

## <a name="to-add-an-atl-control-to-your-project"></a>Aby dodać formant ATL do projektu

1. W **Eksplorator rozwiązań** lub [Widok klasy](/visualstudio/ide/viewing-the-structure-of-code), kliknij prawym przyciskiem myszy nazwę projektu, do którego chcesz dodać prosty obiekt ATL.

1. Kliknij przycisk **Dodaj** z menu skrótów, a następnie kliknij przycisk **Dodaj klasę**.

1. W oknie dialogowym [Dodaj klasę](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) w okienku Szablony kliknij pozycję **formant ATL**, a następnie kliknij przycisk **Dodaj** , aby wyświetlić [Kreatora kontrolki ATL](../../atl/reference/atl-control-wizard.md).

Za pomocą **Kreatora kontrolki ATL** można utworzyć jeden z trzech typów kontrolek:

- Kontrolka standardowa

- Formant złożony

- Kontrolka DHTML

Dodatkowo można zmniejszyć rozmiar kontrolki i usunąć interfejsy, które nie są używane przez większość kontenerów, wybierając **minimalną kontrolę** na stronie **Opcje** kreatora.

## <a name="see-also"></a>Zobacz też

[Dodawanie funkcji do kontrolki złożonej](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[Podstawowe informacje o obiektach COM ATL](../../atl/fundamentals-of-atl-com-objects.md)
