---
description: 'Dowiedz się więcej o programie: korzystanie z istniejącego zestawu rekordów ADO'
title: Korzystanie z istniejącego zestawu rekordów ADO
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 4b5c3b5f621f3cbdba6f2d42fd95436495a5661e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160951"
---
# <a name="using-an-existing-ado-recordset"></a>Korzystanie z istniejącego zestawu rekordów ADO

Aby mieszać OLE DB Szablony konsumentów i obiekty danych aktywnych (ADO), należy użyć obiektów ADO do otwarcia zestawu rekordów (odpowiadającego zestawowi wierszy w szablonach OLE DB konsumentów). W przypadku zestawu rekordów wykonaj następujące czynności, aby nawiązać połączenie z zestawem wierszy OLE DB:

1. Wywoływanie `QueryInterface` `IRowset` wskaźników i `IAccessor` .

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* wskazuje `IUnknown` obiekt zestawu rekordów ADO.

1. Dołącz metodę dostępu i zestaw wierszy do odpowiednich OLE DB klas szablonu użytkownika.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)
