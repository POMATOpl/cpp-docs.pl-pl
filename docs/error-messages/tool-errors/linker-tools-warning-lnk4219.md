---
title: Ostrzeżenie LNK4219 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4219
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
ms.openlocfilehash: 4488539a4f7282180048f1e3530e62e35c3b339e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183101"
---
# <a name="linker-tools-warning-lnk4219"></a>Ostrzeżenie LNK4219 narzędzi konsolidatora

przepełnienie naprawy nazw napraw. Docelowa nazwa symbolu docelowego jest poza zakresem, wstawianie thunk

Konsolidator wstawił thunk w sytuacji, w której nie można dopasować adresu lub przesunięcia w danej instrukcji, ponieważ symbol docelowy jest zbyt daleko od lokalizacji instrukcji.

Można zmienić kolejność obrazów (na przykład za pomocą opcji [/Order](../../build/reference/order-put-functions-in-order.md) ), aby uniknąć dodatkowego poziomu pośredniego.
