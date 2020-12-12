---
description: 'Dowiedz się więcej o: modyfikowanie dziedziczenia RCustomRowset'
title: Modyfikowanie dziedziczenia RCustomRowset
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: c54533122083c526ad12ac6514efa3ad9ba47cf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287011"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>Modyfikowanie dziedziczenia RCustomRowset

Aby dodać `IRowsetLocate` interfejs do prostego przykładowego dostawcy tylko do odczytu, należy zmodyfikować dziedziczenie `CCustomRowset` . Początkowo `CCustomRowset` dziedziczy po `CRowsetImpl` . Należy ją zmodyfikować, aby dziedziczyć `CRowsetBaseImpl` .

W tym celu Utwórz nową klasę, `CCustomRowsetImpl` w polu *niestandardowy* RS. h:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

Teraz Edytuj mapę interfejsu COM w *niestandardowym* RS. h, aby można było wykonać następujące czynności:

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Ten kod tworzy mapę interfejsu COM, która informuje o `CMyRowsetImpl` wywołaniu `QueryInterface` obu `IRowset` `IRowsetLocate` interfejsów i. Aby uzyskać wszystkie implementacje innych klas zestawu wierszy, Mapa łączy klasę z powrotem z `CMyRowsetImpl` `CRowsetBaseImpl` klasą zdefiniowaną przez OLE DB szablonów; Mapa używa makra COM_INTERFACE_ENTRY_CHAIN, które informuje szablony OLE DB do skanowania mapy com w `CRowsetBaseImpl` programie w odpowiedzi na `QueryInterface` wywołanie.

Na koniec Połącz `CCustomRowset` się, `CMyRowsetBaseImpl` modyfikując `CCustomRowset` , aby dziedziczyć z `CMyRowsetImpl` , w następujący sposób:

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` może teraz korzystać z `IRowsetLocate` interfejsu, jednocześnie wykorzystując resztę implementacji klasy zestawu wierszy.

Gdy to zrobisz, możesz [dynamicznie określić kolumny zwracane do konsumenta](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Zobacz też

[Ulepszanie prostego dostawcy Read-Only](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
