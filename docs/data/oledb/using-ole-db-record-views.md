---
description: 'Dowiedz się więcej na temat: korzystanie z widoków rekordów OLE DB'
title: Korzystanie z widoków rekordów OLE DB
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
ms.openlocfilehash: 8230ba118038852f81159d21a51165b7448a26aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332466"
---
# <a name="using-ole-db-record-views"></a>Korzystanie z widoków rekordów OLE DB

Jeśli chcesz wyświetlić OLE DB dane zestawu wierszy w aplikacji MFC, użyj klasy MFC [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Obiekt widoku rekordu utworzony z `COleDBRecordView` umożliwia wyświetlanie rekordów bazy danych w kontrolkach MFC. Widok rekordu to widok formularza okna dialogowego połączony bezpośrednio z obiektem zestawu wierszy OLE DB utworzonym na podstawie `CRowset` klasy szablonu. Pobieranie uchwytu do obiektu zestawu wierszy jest proste:

```cpp
COleDBRecordView myRecordView;
...
// CProductAccessor is a user record class
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();
```

Widok wyświetla pola `CRowset` obiektu w kontrolkach okna dialogowego. `COleDBRecordView`Obiekt używa wymiany danych okna dialogowego (DDX) i funkcji nawigacyjnych wbudowanych w `CRowset` ( `MoveFirst` , `MoveNext` , `MovePrev` i `MoveLast` ) do automatyzacji przenoszenia danych między kontrolkami w formularzu i polami zestawu wierszy. `COleDBRecordView` śledzi położenie użytkownika w zestawie wierszy, aby widok rekordu mógł zaktualizować interfejs użytkownika i dostarcza metodę [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) do aktualizowania bieżącego rekordu przed przejściem do innego.

Możesz użyć funkcji DDX with, `COleDbRecordView` Aby pobrać dane bezpośrednio z zestawu rekordów bazy danych i wyświetlić je w kontrolce okna dialogowego. Użyj metod **DDX_** <strong>\*</strong> (takich jak `DDX_Text` ), a nie funkcji **DDX_Field** <strong>\*</strong> (takich jak `DDX_FieldText` ) `COleDbRecordView` .

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)<br/>
[Klasa COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)<br/>
