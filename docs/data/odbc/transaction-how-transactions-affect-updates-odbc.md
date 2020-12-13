---
description: 'Dowiedz się więcej o: transakcja: jak transakcje wpływają na aktualizacje (ODBC)'
title: 'Transakcja: jak transakcje wpływają na aktualizacje (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 56435d477ab11fe057ec20610a35e75d84cf7340
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333899"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>Transakcja: jak transakcje wpływają na aktualizacje (ODBC)

Aktualizacje [źródła danych](../../data/odbc/data-source-odbc.md) są zarządzane podczas transakcji przy użyciu buforu edycji (ta sama metoda używana poza transakcjami). Elementy członkowskie danych w zestawie rekordów zbiorowo pełnią rolę bufora edycji, który zawiera bieżący rekord, który zestaw rekordów tymczasowo wykonuje kopię zapasową w `AddNew` lub `Edit` . Podczas `Delete` operacji nie jest wykonywana kopia zapasowa bieżącego rekordu w ramach transakcji. Aby uzyskać więcej informacji o buforze edycji i sposobie przechowywania bieżącego rekordu przez aktualizacje, zobacz [zestaw rekordów: jak zestawy rekordów aktualizują rekordy (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

> [!NOTE]
> Jeśli zaimplementowano pobieranie wierszy zbiorczych, nie można wywołać `AddNew` , `Edit` , ani `Delete` . Zamiast tego należy napisać własne funkcje do wykonywania aktualizacji źródła danych. Aby uzyskać więcej informacji na temat pobierania wierszy zbiorczych, zobacz [zestaw rekordów: pobieranie rekordów zbiorczo (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

W trakcie transakcji, `AddNew` , `Edit` i `Delete` operacje mogą być zatwierdzane lub wycofywane. Skutki `CommitTrans` i `Rollback` mogą spowodować, że bieżący rekord nie zostanie przywrócony do buforu edycji. Aby upewnić się, że bieżący rekord jest prawidłowo przywrócony, ważne jest, aby zrozumieć, jak `CommitTrans` i `Rollback` funkcje składowe `CDatabase` pracy z funkcjami aktualizacji `CRecordset` .

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a> Jak CommitTrans ma wpływ na aktualizacje

W poniższej tabeli opisano skutki `CommitTrans` transakcji.

### <a name="how-committrans-affects-updates"></a>Jak CommitTrans ma wpływ na aktualizacje

|Operacja|Stan źródła danych|
|---------------|---------------------------|
|`AddNew` i `Update` , a następnie `CommitTrans`|Nowy rekord zostanie dodany do źródła danych.|
|`AddNew` (bez `Update` ), a następnie `CommitTrans`|Nowy rekord zostanie utracony. Rekord nie został dodany do źródła danych.|
|`Edit` i `Update` , a następnie `CommitTrans`|Zmiany przekazane do źródła danych.|
|`Edit` (bez `Update` ), a następnie `CommitTrans`|Zmiany wprowadzone w rekordzie zostaną utracone. Rekord pozostaje niezmieniony w źródle danych.|
|`Delete` następnie `CommitTrans`|Rekordy zostały usunięte ze źródła danych.|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a> Wpływ wycofywania na transakcje

W poniższej tabeli opisano skutki `Rollback` transakcji.

### <a name="how-rollback-affects-transactions"></a>Wpływ wycofywania na transakcje

|Operacja|Stan bieżącego rekordu|Należy również|Stan źródła danych|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` a `Update` następnie `Rollback`|Zawartość bieżącego rekordu jest tymczasowo przechowywana, aby zwolnić miejsce na nowy rekord. Nowy rekord został wprowadzony do edycji w buforze. Po `Update` wywołaniu, bieżący rekord zostanie przywrócony do buforu edycji.||Dodanie do źródła danych wykonanego przez program `Update` zostało cofnięte.|
|`AddNew` (bez `Update` ), następnie `Rollback`|Zawartość bieżącego rekordu jest tymczasowo przechowywana, aby zwolnić miejsce na nowy rekord. Edycja buforu zawiera nowy rekord.|Wywołaj `AddNew` ponownie, aby przywrócić pusty, nowy rekord. Lub wywołanie `Move` (0) w celu przywrócenia starych wartości do buforu edycji.|Ponieważ `Update` nie został wywołany, nie wprowadzono żadnych zmian w źródle danych.|
|`Edit` a `Update` następnie `Rollback`|Nieedytowana wersja bieżącego rekordu jest tymczasowo przechowywana. Zmiany są wprowadzane do zawartości buforu edycji. Po `Update` wywołaniu, nieedytowana wersja rekordu jest nadal tymczasowo przechowywana.|*Dynamiczny*: przewiń bieżący rekord, a następnie Przywróć nieedytowaną wersję rekordu do buforu edycji.<br /><br /> *Migawka*: Wywołaj `Requery` , aby odświeżyć zestaw rekordów ze źródła danych.|Zmiany wprowadzone w źródle danych `Update` zostały cofnięte.|
|`Edit` (bez `Update` ), następnie `Rollback`|Nieedytowana wersja bieżącego rekordu jest tymczasowo przechowywana. Zmiany są wprowadzane do zawartości buforu edycji.|Wywołaj `Edit` ponownie, aby przywrócić nieedytowaną wersję rekordu do buforu edycji.|Ponieważ `Update` nie został wywołany, nie wprowadzono żadnych zmian w źródle danych.|
|`Delete` następnie `Rollback`|Zawartość bieżącego rekordu jest usuwana.|Wywołaj, `Requery` Aby przywrócić zawartość bieżącego rekordu ze źródła danych.|Anulowano usuwanie danych ze źródła danych.|

## <a name="see-also"></a>Zobacz też

[Transakcja (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Transakcja: wykonywanie transakcji w zestawie rekordów (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[Klasa CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Klasa CRecordset](../../mfc/reference/crecordset-class.md)
