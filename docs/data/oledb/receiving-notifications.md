---
description: 'Dowiedz się więcej na temat: otrzymywanie powiadomień'
title: Odbieranie powiadomień
ms.date: 10/24/2018
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
ms.openlocfilehash: 1885223a7d2b3e932cf449312eab989ecf1d2554
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316885"
---
# <a name="receiving-notifications"></a>Odbieranie powiadomień

OLE DB udostępnia interfejsy do otrzymywania powiadomień w przypadku wystąpienia zdarzeń. Są one opisane w [OLE DB powiadomienia dotyczące obiektów](/previous-versions/windows/desktop/ms725406(v=vs.85)) w **odniesieniu do OLE DB programisty**. Konfiguracja tych zdarzeń używa standardowego mechanizmu punktu połączenia modelu COM. Na przykład obiekt ATL, który chce pobrać zdarzenia przez `IRowsetNotify` implementację `IRowsetNotify` interfejsu poprzez dodanie `IRowsetNotify` do listy pochodnej klasy i udostępnienie go za pomocą makra COM_INTERFACE_ENTRY.

`IRowsetNotify` ma trzy metody, które można wywoływać w różnym czasie. Jeśli chcesz odpowiedzieć tylko na jedną z tych metod, możesz użyć klasy [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , która zwraca E_NOTIMPL dla nieinteresujących Cię metod.

Podczas tworzenia zestawu wierszy należy poinformować dostawcę, że powinien obsługiwać zwracany obiekt zestawu wierszy `IConnectionPointContainer` , który jest wymagany do skonfigurowania powiadomienia.

Poniższy kod przedstawia sposób otwierania zestawu wierszy z obiektu ATL i używania `AtlAdvise` funkcji w celu skonfigurowania ujścia powiadomień. `AtlAdvise` zwraca plik cookie, który jest używany podczas wywoływania `AtlUnadvise` .

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

Następnie używany przez następujący kod:

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)
