---
description: 'Dowiedz się więcej na temat: Klasa CNoAccessor —'
title: CNoAccessor — Klasa
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: 624c72c841280ec56bacf0edd29efeb4b1005988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170389"
---
# <a name="cnoaccessor-class"></a>CNoAccessor — Klasa

Może być używany jako argument szablonu ( `TAccessor` ) dla klas szablonu, takich jak `CCommand` i `CTable` , które wymagają argumentu klasy metody dostępu.

## <a name="syntax"></a>Składnia

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Uwagi

Użyj `CNoAccessor` jako argumentu szablonu, gdy nie chcesz, aby Klasa obsługiwała parametry lub kolumny wyjściowe.

`CNoAccessor` implementuje następujące metody zastępcze, z których każdy odpowiada innym metodom klasy metody dostępu:

- `BindColumns` — Tworzy powiązania kolumn z dostępem do metod dostępu.

- `BindParameters` -Tworzy powiązanie utworzonych parametrów z kolumnami.

- `Bind` -Tworzy powiązania.

- `Close` -Zamyka metodę dostępu.

- `ReleaseAccessors` — Zwalnia metody dostępu utworzone przez klasę.

- `FreeRecordMemory` — Zwalnia wszystkie kolumny w bieżącym rekordzie, które muszą zostać zwolnione.

- `GetColumnInfo` — Pobiera informacje o kolumnie z otwartego zestawu wierszy.

- `GetNumAccessors` — Pobiera liczbę metod dostępu utworzonych przez klasę.

- `IsAutoAccessor` -Zwraca wartość PRAWDA, jeśli dane są automatycznie pobierane dla metody dostępu podczas operacji przenoszenia.

- `GetHAccessor` — Pobiera dojście metody dostępu do określonego akcesora.

- `GetBuffer` — Pobiera wskaźnik do buforu zakładek.

- `NoBindOnNullRowset` -Uniemożliwia powiązanie danych z pustymi zestawami wierszy.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atldbcli. h

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
