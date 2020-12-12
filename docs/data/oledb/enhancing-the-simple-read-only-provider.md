---
description: 'Dowiedz się więcej na temat: ulepszanie prostego dostawcy Read-Only'
title: Udoskonalanie prostego dostawcy tylko do odczytu
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: 00a0ea4fb9b759447026353ba0d78c7c856b15ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317639"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Udoskonalanie prostego dostawcy tylko do odczytu

W tej sekcji przedstawiono sposób ulepszania [prostego dostawcy tylko do odczytu](../../data/oledb/implementing-the-simple-read-only-provider.md) utworzonego w poprzedniej sekcji. `IRowsetLocateImpl` tworzy implementację `IRowsetLocate` interfejsu i dodaje obsługę zakładki.

Gdy korzystasz z działającego dostawcy, możesz go ulepszyć, aby dokonać aktualizacji dostawcy, obsłużyć transakcje lub zwiększyć wydajność algorytmu pobierania wierszy. Większość ulepszeń dostawcy obejmuje dodanie interfejsu do istniejącego obiektu COM.

Przykład w poniższych tematach rozszerza mechanizm pobierania wierszy, dodając `IRowsetLocate` interfejs do programu `CAgentRowset` . Tematy pokazują, jak:

- [Ustaw RCustomRowset z IRowsetLocate](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).

- [Dynamiczne Określanie kolumn zwracanych do konsumenta](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Zobacz też

[Tworzenie prostego dostawcy Read-Only](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
