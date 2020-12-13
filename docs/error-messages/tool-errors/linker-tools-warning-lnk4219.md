---
description: 'Dowiedz się więcej o: LNK4219 ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4219 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4219
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
ms.openlocfilehash: 2d9e720ba358b109aca1ade634009985e83974be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150582"
---
# <a name="linker-tools-warning-lnk4219"></a>Ostrzeżenie LNK4219 narzędzi konsolidatora

przepełnienie naprawy nazw napraw. Docelowa nazwa symbolu docelowego jest poza zakresem, wstawianie thunk

Konsolidator wstawił thunk w sytuacji, w której nie można dopasować adresu lub przesunięcia w danej instrukcji, ponieważ symbol docelowy jest zbyt daleko od lokalizacji instrukcji.

Można zmienić kolejność obrazów (na przykład za pomocą opcji [/Order](../../build/reference/order-put-functions-in-order.md) ), aby uniknąć dodatkowego poziomu pośredniego.
