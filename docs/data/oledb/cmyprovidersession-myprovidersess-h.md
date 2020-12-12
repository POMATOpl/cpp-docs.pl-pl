---
description: 'Dowiedz się więcej o: CCustomSession (CustomSess. H)'
title: CCustomSession (CustomSess.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
ms.openlocfilehash: 0c090e01b5cef1bc0fccad8a1c23948fb9ea09b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170428"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*Niestandardowe* Sess. H zawiera deklarację i implementację dla obiektu sesji OLE DB. Obiekt źródła danych tworzy obiekt sesji i reprezentuje konwersację między odbiorcą i dostawcą. Kilka równoczesnych sesji może być otwartych dla jednego źródła danych. Lista dziedziczenia jest `CCustomSession` następująca:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSession
class ATL_NO_VTABLE CCustomSession :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IGetDataSourceImpl<CCustomSession>,
   public IOpenRowsetImpl<CCustomSession>,
   public ISessionPropertiesImpl<CCustomSession>,
   public IObjectWithSiteSessionImpl<CCustomSession>,
   public IDBSchemaRowsetImpl<CCustomSession>,
   public IDBCreateCommandImpl<CCustomSession, CCustomCommand>
```

Obiekt Session dziedziczy z `IGetDataSource` , `IOpenRowset` , `ISessionProperties` , i `IDBCreateCommand` . `IGetDataSource`Interfejs umożliwia sesji do pobrania źródła danych, które je utworzyło. Jest to przydatne, jeśli trzeba uzyskać właściwości ze źródła danych, które zostało utworzone przez Ciebie, lub inne informacje, które może dostarczyć źródło danych. `ISessionProperties`Interfejs obsługuje wszystkie właściwości sesji. `IOpenRowset`Interfejsy i służą `IDBCreateCommand` do działania bazy danych. Jeśli dostawca obsługuje polecenia, implementuje `IDBCreateCommand` interfejs. Służy do tworzenia obiektu polecenia, który może wykonywać polecenia. Dostawca zawsze implementuje `IOpenRowset` obiekt. Służy do generowania zestawu wierszy od dostawcy. Jest to domyślny zestaw wierszy (na przykład `"select * from mytable"` ) od dostawcy.

Kreator generuje również trzy klasy sesji: `CCustomSessionColSchema` , `CCustomSessionPTSchema` , i `CCustomSessionTRSchema` . Te sesje są używane dla zestawów wierszy schematu. Zestawy wierszy schematu umożliwiają dostawcy zwracanie metadanych do konsumenta bez konieczności wykonywania zapytania lub pobierania danych. Pobieranie metadanych może być bardzo szybsze niż znalezienie możliwości dostawcy.

Specyfikacja OLE DB wymaga, aby dostawcy implementujący `IDBSchemaRowset` interfejs obsługiwały trzy typy zestawów wierszy schematu: DBSCHEMA_COLUMNS, DBSCHEMA_PROVIDER_TYPES i DBSCHEMA_TABLES. Kreator generuje implementacje dla każdego zestawu wierszy schematu. Każda Klasa wygenerowana przez kreatora zawiera `Execute` metodę. W tej `Execute` metodzie można zwrócić do dostawcy dane dotyczące tabel, kolumn i typów danych obsługiwanych przez użytkownika. Te dane są znane w czasie kompilacji.

## <a name="see-also"></a>Zobacz też

[Pliki Wizard-Generated dostawcy](../../data/oledb/provider-wizard-generated-files.md)<br/>
