---
description: 'Dowiedz się więcej o: Brak powiązania'
title: Brak połączenia
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: cf0e1ccbbea3b79bce66335e361f3c23162e6cb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243318"
---
# <a name="no-linkage"></a>Brak połączenia

Jeśli deklaracja identyfikatora w bloku nie zawiera **`extern`** specyfikatora klasy magazynowania, identyfikator nie ma powiązania i jest unikatowy dla funkcji.

Następujące identyfikatory nie mają powiązania:

- Identyfikator zadeklarowany jako coś innego niż obiekt lub funkcja

- Identyfikator zadeklarowany jako parametr funkcji

- Identyfikator zakresu bloku dla obiektu zadeklarowanego bez **`extern`** specyfikatora klasy magazynu

Jeśli identyfikator nie ma powiązania, zadeklarowanie tej samej nazwy (w Deklarator lub specyfikatorze typu) na tym samym poziomie zakresu generuje błąd ponownej definicji symbolu.

## <a name="see-also"></a>Zobacz też

[Użycie zewnętrznie w celu określenia powiązania](../cpp/extern-cpp.md)
