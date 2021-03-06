---
description: 'Dowiedz się więcej na temat: Transaction (ODBC)'
title: Transakcja (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
ms.openlocfilehash: a7b769c37b58b34433939a18cb0dccf5fb4a798d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333875"
---
# <a name="transaction-odbc"></a>Transakcja (ODBC)

Ten temat dotyczy klas MFC ODBC.

Transakcja to metoda grupowania lub wsadowego szeregu aktualizacji [źródła danych](../../data/odbc/data-source-odbc.md) , dzięki czemu wszystkie są zatwierdzane jednocześnie lub nie są one zatwierdzane w przypadku wycofania transakcji. Jeśli transakcja nie zostanie użyta, zmiany w źródle danych są zatwierdzane automatycznie, a nie na żądanie.

> [!NOTE]
> Nie wszystkie sterowniki baz danych ODBC obsługują transakcje. Wywołaj `CanTransact` funkcję członkowską obiektu [CDatabase](../../mfc/reference/cdatabase-class.md) lub [CRecordset](../../mfc/reference/crecordset-class.md) , aby określić, czy sterownik obsługuje transakcje dla danej bazy danych. Należy pamiętać, że program nie informuje o tym, `CanTransact` czy źródło danych zapewnia pełną obsługę transakcji. Należy również wywołać `CDatabase::GetCursorCommitBehavior` i `CDatabase::GetCursorRollbackBehavior` po i `CommitTrans` , `Rollback` Aby sprawdzić efekt transakcji w otwartym `CRecordset` obiekcie.

Wywołania `AddNew` `Edit` funkcji i elementów członkowskich `CRecordset` obiektu mają wpływ na źródło danych natychmiast po wywołaniu `Update` . `Delete` wywołania również zaczną obowiązywać natychmiast. Z kolei można użyć transakcji składającej się z wielu wywołań do `AddNew` , `Edit` , `Update` , i `Delete` , które są wykonywane, ale nie są zatwierdzone, dopóki nie zostanie jawnie wywołana `CommitTrans` . Ustanawiając transakcję, można wykonać serię takich wywołań, jednocześnie zachowując możliwość wycofania ich z powrotem. Jeśli zasób krytyczny jest niedostępny lub jakiś inny warunek uniemożliwia ukończenie całej transakcji, można wycofać transakcję zamiast jej zatwierdzania. W takim przypadku żadna ze zmian należących do transakcji nie ma wpływu na źródło danych.

> [!NOTE]
> Obecnie Klasa nie `CRecordset` obsługuje aktualizacji źródła danych, jeśli wdrożono pobieranie wierszy zbiorczych. Oznacza to, że nie można wykonywać wywołań do `AddNew` , `Edit` , `Delete` , lub `Update` . Można jednak napisać własne funkcje do wykonywania aktualizacji, a następnie wywoływać te funkcje w ramach danej transakcji. Aby uzyskać więcej informacji na temat pobierania wierszy zbiorczych, zobacz [zestaw rekordów: pobieranie rekordów zbiorczo (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
> Poza wpływem zestawu rekordów, transakcje wpływają na instrukcje SQL wykonywane bezpośrednio, o ile używasz ODBC **HDBC** skojarzonego z `CDatabase` obiektem lub ODBC **HSTMT** w oparciu o te **HDBC**.

Transakcje są szczególnie przydatne w przypadku, gdy istnieje wiele rekordów, które muszą być aktualizowane jednocześnie. W tym przypadku chcemy uniknąć transakcji o połowie ukończonej, takiej jak może się zdarzyć, jeśli wyjątek został zgłoszony przed ostatnią aktualizacją. Zgrupowanie takich aktualizacji do transakcji umożliwia odzyskiwanie (wycofywanie) ze zmian i zwraca rekordy do stanu sprzed transakcji. Jeśli na przykład Bank transferuje pieniądze z konta A do konta B, zarówno wycofanie od a i kaucji do B muszą pomyślnie przetworzyć odpowiednie środki lub cała transakcja nie powiedzie się.

W klasach baz danych transakcje są wykonywane za pomocą `CDatabase` obiektów. `CDatabase`Obiekt reprezentuje połączenie ze źródłem danych, a jeden lub więcej zestawów rekordów skojarzonych z tym `CDatabase` obiektem operuje na tabelach bazy danych za pomocą funkcji składowych zestawu rekordów.

> [!NOTE]
> Obsługiwany jest tylko jeden poziom transakcji. Nie można zagnieżdżać transakcji ani nie może obejmować wielu obiektów bazy danych.

Poniższe tematy zawierają więcej informacji o sposobie wykonywania transakcji:

- [Transakcja: wykonywanie transakcji w zestawie rekordów (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [Transakcja: jak transakcje wpływają na aktualizacje (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>Zobacz też

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
