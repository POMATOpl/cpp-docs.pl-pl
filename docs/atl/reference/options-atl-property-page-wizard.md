---
title: Opcje, Kreator strony właściwości ATL
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: 74cf72feedd8dc8e1186d54a8abe840195964620
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923660"
---
# <a name="options-atl-property-page-wizard"></a>Opcje, Kreator strony właściwości ATL

::: moniker range="msvc-160"

Kreator strony właściwości ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

Użyj tej strony kreatora, aby zdefiniować model wątkowości i poziom agregacji tworzonej strony właściwości.

- **Model wątkowości**

   Określa model wątkowości używany przez stronę właściwości.

   Aby uzyskać więcej informacji [, zobacz Określanie modelu wątkowości projektu](../../atl/specifying-the-threading-model-for-a-project-atl.md) .

   |Opcja|Opis|
   |------------|-----------------|
   |**Pojedynczy**|Strona właściwości jest uruchamiana tylko w podstawowym wątku COM.|
   |**Apartamentu**|Stronę właściwości można utworzyć w dowolnym elemencie Apartment pojedynczego wątku. Domyślnie.|

- **Agregacja**

   Dodaje obsługę agregacji dla tworzonej strony właściwości. Aby uzyskać więcej informacji, zobacz [agregacja](../../atl/aggregation.md) .

   |Opcja|Opis|
   |------------|-----------------|
   |**Tak**|Utwórz stronę właściwości, którą można agregować.|
   |**Nie**|Utwórz stronę właściwości, której nie można agregować.|
   |**Jedyn**|Utwórz stronę właściwości, która może być tworzona tylko przy użyciu agregacji.|

::: moniker-end

## <a name="see-also"></a>Zobacz także

[Kreator strony właściwości ATL](../../atl/reference/atl-property-page-wizard.md)<br/>
[Ciągi, Kreator strony właściwości ATL](../../atl/reference/strings-atl-property-page-wizard.md)
