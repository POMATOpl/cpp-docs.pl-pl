---
description: 'Dowiedz się więcej na temat: Pobieranie obiektu BLOB'
title: Pobieranie obiektu BLOB
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: ef870d84c286f72621e87858cea944cc70cbe0cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286608"
---
# <a name="retrieving-a-blob"></a>Pobieranie obiektu BLOB

Na różne sposoby można pobrać binarny duży obiekt (BLOB). Możesz użyć, `DBTYPE_BYTES` Aby pobrać obiekt BLOB jako sekwencję bajtów lub użyć interfejsu, takiego jak `ISequentialStream` . Aby uzyskać więcej informacji, zobacz [obiekty blob i obiektów OLE](/previous-versions/windows/desktop/ms711511(v=vs.85)) w **Kompendium OLE DB programisty**.

Poniższy kod przedstawia sposób pobierania obiektu BLOB za pomocą polecenia `ISequentialStream` . Makro [BLOB_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#blob_entry) umożliwia określenie interfejsu i flag używanych dla interfejsu. Po otwarciu tabeli, kod wywołuje `Read` się wielokrotnie w `ISequentialStream` celu odczytu bajtów z obiektu BLOB. Kod wywołuje metodę `Release` Dispose wskaźnika interfejsu przed wywołaniem `MoveNext` do pobrania następnego rekordu.

```cpp
class CCategories
{
public:
   ISequentialStream* pPicture;

BEGIN_COLUMN_MAP(CCategories)
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)
END_COLUMN_MAP()
};
```

Następnie używany przez następujący kod:

```cpp
CTable<CAccessor<CCategories>> categories;
ULONG cb;
BYTE myBuffer[65536];

categories.Open(session, "Categories");

while (categories.MoveNext() == S_OK)
{
   do
   {
      categories.pPicture->Read(myBuffer, 65536, &cb);
      // Do something with the buffer
   } while (cb > 0);
   categories.pPicture->Release();
}
```

Aby uzyskać więcej informacji na temat makr, które obsługują dane obiektów BLOB, zobacz **makra mapy kolumn** w [makrach i funkcjach globalnych dla OLE DB szablonów konsumentów](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)<br/>
[Makra i funkcje globalne dla OLE DB szablonów konsumentów](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
