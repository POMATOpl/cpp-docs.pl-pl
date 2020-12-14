---
description: 'Dowiedz się więcej na temat: Klasa Ccolumnaccessor —'
title: CColumnAccessor — Klasa
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 7551f39d34bb4f13b4ffae358db05aede2adb9e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335517"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor — Klasa

Generuje wstrzykiwany kod klienta.

## <a name="syntax"></a>Składnia

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Uwagi

W kodzie wstrzykiwanym każda kolumna jest powiązana jako oddzielna metoda dostępu. Należy pamiętać, że ta klasa jest używana w wstrzykiwanym kodzie (na przykład może wystąpić podczas debugowania), ale zazwyczaj nie trzeba używać jej bezpośrednio ani jej metod.

`CColumnAccessor` implementuje następujące metody zastępcze, z których każdy odpowiada w działaniu z innymi metodami klasy metody dostępu:

- `CColumnAccessor` Konstruktor; tworzy wystąpienia i inicjuje `CColumnAccessor` obiekt.

- `CreateAccessor` Przydziela pamięć dla struktur powiązań kolumn i inicjuje elementy członkowskie danych kolumny.

- `BindColumns` Tworzy powiązania kolumn z dostępem.

- `SetParameterBuffer` Przydziela bufory dla parametrów.

- `AddParameter` Dodaje wpis parametru do struktur wpisów parametrów.

- `HasOutputColumns` Określa, czy akcesor ma kolumny wyjściowe

- `HasParameters` Określa, czy metoda dostępu ma parametry.

- `BindParameters` Tworzy powiązanie utworzonych parametrów z kolumnami.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atldbcli. h

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
