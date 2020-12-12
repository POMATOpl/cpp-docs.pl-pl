---
description: Dowiedz się więcej na temat interfejsów obiektów źródła danych
title: Interfejsy obiektu źródła danych
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: ecc37ca4286e288939ccd15bdcd073379c27f7c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287622"
---
# <a name="data-source-object-interfaces"></a>Interfejsy obiektu źródła danych

W poniższej tabeli przedstawiono obowiązkowe i opcjonalne interfejsy zdefiniowane przez OLE DB dla obiektu źródła danych.

|Interfejs|Wymagane?|Zaimplementowane przez OLE DB szablony?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|Obowiązkowy|Tak|
|`IDBInitialize`|Obowiązkowy|Tak|
|`IDBProperties`|Obowiązkowy|Tak|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|Obowiązkowy|Tak|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Opcjonalne|Nie|
|`IDBDataSourceAdmin`|Opcjonalne|Nie|
|`IDBInfo`|Opcjonalne|Nie|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|Opcjonalne|Nie|
|`ISupportErrorInfo`|Opcjonalne|Nie|

Obiekt źródła danych implementuje `IDBProperties` `IDBInitialize` interfejsy, i `IDBCreateSession` przez dziedziczenie. Możesz wybrać obsługę dodatkowych funkcji, dziedzicząc lub niedziedzicząc z jednej z tych klas implementacji. Jeśli chcesz obsługiwać `IDBDataSourceAdmin` interfejs, musisz dziedziczyć z `IDBDataSourceAdminImpl` klasy.

## <a name="see-also"></a>Zobacz też

[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
