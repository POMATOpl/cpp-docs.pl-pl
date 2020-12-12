---
description: 'Dowiedz się więcej na temat: Klasa CAccessor'
title: Klasa CAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: 26b03bc3f464ce606194d6835953c39969bde5de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319173"
---
# <a name="caccessor-class"></a>Klasa CAccessor

Reprezentuje jeden z typów metod dostępu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>Parametry

*T*<br/>
Klasa rekordu użytkownika.

## <a name="remarks"></a>Uwagi

Jest on używany, gdy rekord jest statycznie powiązany ze źródłem danych. Rekord zawiera bufor. Ta klasa obsługuje wiele metod dostępu w zestawie wierszy.

Użyj tego typu metody dostępu, gdy znasz strukturę i typ bazy danych.

Jeśli metoda dostępu zawiera pola, które wskazują na pamięć (na przykład `BSTR` interfejs lub), które muszą zostać zwolnione, wywołaj funkcję członkowską [CAccessorRowset:: FreeRecordMemory](./caccessorrowset-class.md#freerecordmemory) przed odczytaniem następnego rekordu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atldbcli. h

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
