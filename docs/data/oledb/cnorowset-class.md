---
description: 'Dowiedz się więcej na temat: Klasa CNoRowset —'
title: CNoRowset — Klasa
ms.date: 11/04/2016
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
ms.openlocfilehash: 4cdb4631b63ec1f013183713900ffd9574d90fc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307564"
---
# <a name="cnorowset-class"></a>CNoRowset — Klasa

Może służyć jako argument szablonu ( `TRowset` ) dla [CCommand](../../data/oledb/ccommand-class.md) lub [CTable](../../data/oledb/ctable-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>Parametry

*TAccessor*<br/>
Klasa akcesora. Wartość domyślna to `CAccessorBase`.

## <a name="remarks"></a>Uwagi

Użyj `CNoRowset` jako argumentu szablonu, jeśli polecenie nie zwraca zestawu wierszy.

`CNoRowset` implementuje następujące metody zastępcze, z których każdy odpowiada innym metodom klasy metody dostępu:

- `BindFinished` -Wskazuje, kiedy wiązanie jest kompletne (zwraca `S_OK` ).

- `Close` -Zwalnia wiersze i bieżący interfejs IRowset.

- `GetIID` — Pobiera identyfikator interfejsu punktu połączenia.

- `GetInterface` — Pobiera interfejs.

- `GetInterfacePtr` — Pobiera wskaźnik hermetyzowanego interfejsu.

- `SetAccessor` -Ustawia wskaźnik na metodę dostępu.

- `SetupOptionalRowsetInterfaces` -Konfiguruje opcjonalne interfejsy dla zestawu wierszy.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atldbcli. h

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
