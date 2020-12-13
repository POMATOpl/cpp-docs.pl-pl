---
description: 'Dowiedz się więcej o: zestaw rekordów: zbiorcze Dodawanie rekordów (ODBC)'
title: 'Zestaw rekordów: zbiorcze dodawanie rekordów (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: 5cb47fc8e96a38b2e5cc6c83cf464f28f2a85aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340401"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Zestaw rekordów: zbiorcze dodawanie rekordów (ODBC)

Ten temat dotyczy klas MFC ODBC.

Klasa MFC [CRecordset](../../mfc/reference/crecordset-class.md) ma nową optymalizację, która zwiększa wydajność, gdy do tabeli są dodawane nowe rekordy.

> [!NOTE]
> Ten temat dotyczy obiektów pochodnych `CRecordset` , w których nie zaimplementowano pobierania wierszy zbiorczych. Jeśli używasz pobierania wierszy zbiorczych, zobacz [zestaw rekordów: pobieranie rekordów zbiorczo (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Nowa opcja dla parametru *dwOptions* do funkcji [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) member, `optimizeBulkAdd` , która zwiększa wydajność w przypadku dodawania wielu rekordów po kolei bez wywoływania `Requery` lub `Close` . Tylko pola, które są zanieczyszczone przed pierwszym `Update` wywołaniem są oznaczone jako zanieczyszczone dla kolejnych `AddNew` / `Update` wywołań.

Jeśli używasz klas baz danych, aby korzystać z `::SQLSetPos` funkcji interfejsu API ODBC do dodawania, edytowania i usuwania rekordów, Ta optymalizacja nie jest konieczna.

Jeśli Biblioteka kursorów ODBC jest załadowana lub sterownik ODBC nie obsługuje dodawania, edytowania i usuwania za pośrednictwem programu `::SQLSetPos` , Ta optymalizacja powinna zwiększyć wydajność zbiorczą. Aby włączyć tę optymalizację, należy ustawić parametr *dwOptions* w `Open` wywołaniu zestawu rekordów:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>Zobacz też

[Zestaw rekordów (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Zestaw rekordów: Dodawanie, aktualizowanie i usuwanie rekordów (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Zestaw rekordów: blokowanie rekordów (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
