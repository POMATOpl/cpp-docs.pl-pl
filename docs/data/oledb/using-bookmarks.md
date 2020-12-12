---
description: 'Dowiedz się więcej o programie: używanie zakładek'
title: Korzystanie z zakładek
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: d0cf27a5f93b3e6b00fa6f8cbb69ae7414f4d819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319160"
---
# <a name="using-bookmarks"></a>Korzystanie z zakładek

Przed otwarciem zestawu wierszy należy poinformować dostawcę, którego ma używać zakładek. W tym celu należy ustawić `DBPROP_BOOKMARKS` Właściwość na **`true`** wartość w ustawieniu właściwości. Dostawca pobiera zakładki jako kolumny zero, dlatego należy użyć specjalnego makra BOOKMARK_ENTRY i klasy, jeśli używasz `CBookmark` statycznej metody dostępu. `CBookmark` jest klasą szablonu, w której argument jest długością w bajtach buforu zakładki. Długość buforu wymaganego dla zakładki zależy od dostawcy. Jeśli używasz dostawcy OLE DB ODBC, jak pokazano w poniższym przykładzie, bufor musi mieć 4 bajty.

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

Następnie używany przez następujący kod:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

Jeśli używasz `CDynamicAccessor` , bufor jest ustawiany dynamicznie w czasie wykonywania. W takim przypadku można użyć wyspecjalizowanej wersji programu, `CBookmark` dla której nie zostanie określona długość buforu. Użyj funkcji, `GetBookmark` Aby pobrać zakładkę z bieżącego rekordu, jak pokazano w tym przykładzie kodu:

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

Aby uzyskać informacje na temat obsługi zakładek w dostawcach, zobacz [obsługa dostawców dla zakładek](../../data/oledb/provider-support-for-bookmarks.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)
