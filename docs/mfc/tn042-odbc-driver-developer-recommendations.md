---
description: 'Dowiedz się więcej na temat: TN042: zalecenia dla deweloperów sterowników ODBC'
title: 'TN042: zalecenia dla deweloperów sterowników ODBC'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 896c99ffeba98f1ea38771676475c85abf13d983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215303"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: zalecenia dla deweloperów sterowników ODBC

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje wskazówki dotyczące składników zapisywania sterowników ODBC. Zawiera opis ogólnych wymagań i założeń funkcji ODBC, które tworzą klasy baz danych MFC i różne oczekiwane szczegóły semantyczne. Wymagania dotyczące funkcjonalności sterowników obsługują trzy `CRecordset` otwarte tryby (**ForwardOnly**, **Snapshot** i **dynamiczny**).

## <a name="odbcs-cursor-library"></a>Biblioteka kursorów ODBC

Klasy baz danych MFC udostępniają użytkownikowi funkcje, które w wielu przypadkach przekraczają funkcje udostępniane przez większość sterowników ODBC na poziomie 1. Na szczęście Biblioteka kursorów ODBC będzie sama warstwą między klasami baz danych a sterownikiem i automatycznie udostępnia większość tej dodatkowej funkcjonalności.

Na przykład większość sterowników 1,0 nie obsługuje przewijania wstecz. Biblioteka kursorów może je wykryć i będzie buforować wiersze ze sterownika i przedstawić je zgodnie z żądaniem FETCH_PREV wywołań w `SQLExtendedFetch` .

Innym ważnym przykładem zależności biblioteki kursora jest aktualizacja położenia. Większość sterowników 1,0 również nie ma opcji aktualizacje pozycjonowane, ale Biblioteka kursorów generuje instrukcje aktualizacji, które identyfikują wiersz docelowy źródła danych na podstawie bieżących wartości danych w pamięci podręcznej lub zbuforowanej wartości sygnatury czasowej.

Biblioteka klas nigdy nie używa wielu zestawów wierszy. W związku z tym kilka `SQLSetPos` instrukcji są zawsze stosowane do wiersza 1 zestawu wierszy.

## <a name="cdatabases"></a>CDatabases

Każdy `CDatabase` z nich przypisuje pojedynczy **HDBC**. (Jeśli `CDatabase` `ExecuteSQL` jest używana funkcja, **HSTMT** jest tymczasowo przydzielono). W przypadku konieczności wielokrotności należy `CDatabase` obsługiwać wiele **HDBC** s na **HENV** .

Klasy baz danych wymagają biblioteki kursora. Jest to odzwierciedlone w `SQLSetConnections` **SQL_ODBC_CURSORS** wywołań, **SQL_CUR_USE_ODBC**.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** jest używany przez program `CDatabase::Open` w celu nawiązania połączenia ze źródłem danych.

Sterownik musi obsługiwać `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**, `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**.

Aby transakcje były obsługiwane dla `CDatabase` i zależne zestawy rekordów, `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` a **SQL_CURSOR_ROLLBACK_BEHAVIOR** muszą mieć **SQL_CR_PRESERVE**. W przeciwnym razie próby przeprowadzenia kontroli transakcji zostaną zignorowane.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` musi być obsługiwany. Jeśli zwróci wartość "Y", nie będą wykonywane żadne operacje aktualizacji w źródle danych.

W przypadku `CDatabase` otwarcia elementu ReadOnly próba ustawienia tylko do odczytu źródła danych zostanie podjęta z `SQLSetConnectOption SQL_ACCESS_MODE` , **SQL_MODE_READ_ONLY**.

Jeśli identyfikatory wymagają nakładania, te informacje powinny być zwracane ze sterownika z `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` wywołaniem.

Na potrzeby debugowania, `SQLGetInfo SQL_DBMS_VER` a **SQL_DBMS_NAME** są pobierane ze sterownika.

`SQLSetStmtOption SQL_QUERY_TIMEOUT` i **SQL_ASYNC_ENABLE** mogą być wywoływane na `CDatabase` **HDBC**.

`SQLError` może być wywoływana z dowolnego lub wszystkich argumentów NULL.

Oczywiście, `SQLAllocEnv` `SQLAllocConnect` `SQLDisconnect` i `SQLFreeConnect` muszą być obsługiwane.

## <a name="executesql"></a>ExecuteSql by

Oprócz przydzielania i zwalniania tymczasowych **HSTMT**, `ExecuteSQL` wywołań `SQLExecDirect` , `SQLFetch` `SQLNumResultCol` i `SQLMoreResults` . `SQLCancel` może być wywoływana na **HSTMT**.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` zostanie wywołana.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, wycofywanie

`SQLSetConnectOption SQL_AUTOCOMMIT` i `SQLTransact SQL_COMMIT` , **SQL_ROLLBACK** i **SQL_AUTOCOMMIT** będą wywoływane, jeśli są wykonywane żądania transakcji.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`, `SQLPrepare` , `SQLExecute` (Dla `Open` i `Requery` ), `SQLExecDirect` (dla operacji aktualizacji) `SQLFreeStmt` musi być obsługiwany. `SQLNumResultCols` i `SQLDescribeCol` zostanie wywołana dla wyników ustawionych w różnym czasie.

`SQLSetParam` jest szeroko używany do wiązania danych parametrów i funkcji **DATA_AT_EXEC** .

`SQLBindCol` jest szeroko używany do rejestrowania lokalizacji przechowywania danych kolumn wyjściowych za pomocą ODBC.

Dwa `SQLGetData` wywołania są używane do pobierania danych **SQL_LONG_VARCHAR** i **SQL_LONG_VARBINARY** . Pierwsze wywołanie próbuje znaleźć łączną długość wartości kolumny przez wywołanie `SQLGetData` z cbMaxValueą 0, ale z prawidłowym pcbValue. Jeśli pcbValue utrzymuje **SQL_NO_TOTAL**, zostanie zgłoszony wyjątek. W przeciwnym razie jest przydzielono **HGLOBAL** i inne `SQLGetData` wywołanie w celu pobrania całego wyniku.

## <a name="updating"></a>Aktualizowanie

Jeśli zażądano blokowania pesymistycznego, `SQLGetInfo SQL_LOCK_TYPES` będą wykonywane zapytania. Jeśli **SQL_LCK_EXCLUSIVE** nie jest obsługiwana, zostanie zgłoszony wyjątek.

Próby zaktualizowania `CRecordset` (**migawka** lub **dynamiczny**) spowodują przydzielenie sekundy **HSTMT** . W przypadku sterowników, które nie obsługują drugiego **HSTMT**, Biblioteka kursorów symuluje tę funkcjonalność. Niestety, czasami może to oznaczać, że przed przetworzeniem żądania drugiego **HSTMT** zostanie wymuszone wykonanie bieżącego zapytania przy pierwszym **HSTMT** .

`SQLFreeStmt SQL_CLOSE` i **SQL_RESET_PARAMS** i `SQLGetCursorName` będą wywoływane podczas operacji aktualizacji.

Jeśli w **outputColumns** znajdują się **CLongBinarys** , musi być obsługiwana funkcja **DATA_AT_EXEC** ODBC. Obejmuje to zwracanie **SQL_NEED_DATA** z `SQLExecDirect` , `SQLParamData` i `SQLPutData` .

`SQLRowCount` jest wywoływana po wykonaniu, aby sprawdzić, czy tylko jeden rekord został zaktualizowany przez `SQLExecDirect` .

## <a name="forwardonly-cursors"></a>ForwardOnly kursory

`SQLFetch`Jest to wymagane tylko w przypadku `Move` operacji. Należy zauważyć, że kursory **ForwardOnly** nie obsługują aktualizacji.

## <a name="snapshot-cursors"></a>Kursory migawek

Funkcja migawek wymaga `SQLExtendedFetch` obsługi. Jak wspomniano powyżej, Biblioteka kursorów ODBC będzie wykrywać, kiedy sterownik nie obsługuje `SQLExtendedFetch` , i zapewniać potrzebną pomoc techniczną.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** musi obsługiwać **SQL_SO_STATIC**.

## <a name="dynaset-cursors"></a>Kursory dynamiczny

Poniżej znajduje się minimalna pomoc techniczna wymagana do otwarcia zestawu dynamicznego:

`SQLGetInfo`, **SQL_ODBC_VER** musi zwrócić > "01".

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** musi obsługiwać **SQL_SO_KEYSET_DRIVEN**.

`SQLGetInfo`, **SQL_ROW_UPDATES** musi zwrócić wartość "Y".

`SQLGetInfo`, **SQL_POSITIONED_UPDATES** musi obsługiwać **SQL_PS_POSITIONED_DELETE** i **SQL_PS_POSITIONED_UPDATE**.

Ponadto, jeśli zażądano blokowania pesymistycznego, zostanie wywołane wywołanie `SQLSetPos` z IRow 1, FREFRESH false i **SQL_LCK_EXCLUSIVE** hodowlane.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
