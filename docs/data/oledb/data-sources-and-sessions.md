---
description: 'Dowiedz się więcej o: źródła danych i sesje'
title: Źródła i sesje danych
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 352bce1140ef8aebdc198ad237f4a427d5f9c440
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287661"
---
# <a name="data-sources-and-sessions"></a>Źródła i sesje danych

Na poniższej ilustracji przedstawiono klasy, które obsługują łączenie się ze źródłem danych i uzyskiwanie do niego dostępu. Każda klasa jest oparta na standardowej implementacji składnika OLE DB.

![Klasy źródła danych i sesji](../../data/oledb/media/vcdatasourcesessionclasses.gif "Klasy źródła danych i sesji") <br/>
Klasy źródła danych i sesji

Klasy są:

- [CDataSource](../../data/oledb/cdatasource-class.md) Ta klasa tworzy wystąpienie obiektu źródła danych, który umożliwia utworzenie połączenia ze źródłem danych i zarządzanie nim za pomocą dostawcy OLE DB. Źródło danych pobiera informacje takie jak adres źródła danych i informacje uwierzytelniania w postaci parametrów połączenia.

   Warto również zauważyć, że Klasa pomocnika [CEnumerator](../../data/oledb/cenumerator-class.md) jest często używana przed nawiązaniem połączenia w celu uzyskania listy dostępnych dostawców zarejestrowanych w systemie. Pozwala to wybrać dostawcę jako źródło danych. Na przykład okno dialogowe **Właściwości łącza danych** używa tej klasy do wypełniania listy dostawców na karcie **dostawcy** . Jest ono równe `SQLBrowseConnect` `SQLDriverConnect` funkcji or.

- [CSession](../../data/oledb/csession-class.md) Ta klasa tworzy wystąpienie obiektu Session, który reprezentuje pojedynczą sesję dostępu do źródła danych. Można jednak utworzyć wiele sesji w źródle danych. Dla każdej sesji można utworzyć zestawy wierszy, polecenia i inne obiekty, aby uzyskać dostęp do danych ze źródła danych. Sesja obsługuje transakcje.

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)
