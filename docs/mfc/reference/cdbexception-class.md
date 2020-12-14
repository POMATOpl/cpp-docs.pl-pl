---
description: 'Dowiedz się więcej na temat: Klasa CDBException'
title: Klasa CDBException
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: 8e337cc0f66a4a281de07ba3839895096e8021d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222128"
---
# <a name="cdbexception-class"></a>Klasa CDBException

Reprezentuje warunek wyjątku wynikający z klas baz danych.

## <a name="syntax"></a>Składnia

```
class CDBException : public CException
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CDBException:: m_nRetCode](#m_nretcode)|Zawiera kod powrotu Open Database Connectivity (ODBC) typu RETCODE.|
|[CDBException:: m_strError](#m_strerror)|Zawiera ciąg, który opisuje błąd w wyrażeniach alfanumerycznych.|
|[CDBException:: m_strStateNativeOrigin](#m_strstatenativeorigin)|Zawiera ciąg opisujący błąd w warunkach kodów błędów zwracanych przez ODBC.|

## <a name="remarks"></a>Uwagi

Klasa zawiera dwa publiczne elementy członkowskie danych, których można użyć do określenia przyczyny wyjątku lub wyświetlenia wiadomości tekstowej opisującej wyjątek. `CDBException` obiekty są konstruowane i zgłaszane przez funkcje składowe klas baz danych.

> [!NOTE]
> Ta klasa jest jedną z klas Open Database Connectivity MFC (ODBC). Jeśli zamiast tego używasz nowszych klas obiektów dostępu do danych (DAO), zamiast tego użyj [CDaoException](../../mfc/reference/cdaoexception-class.md) . Wszystkie nazwy klas DAO mają jako prefiks "CDao". Aby uzyskać więcej informacji, zobacz [Omówienie artykułu: Programowanie baz danych](../../data/data-access-programming-mfc-atl.md).

Wyjątkami są przypadki nietypowego wykonywania, w tym warunki poza kontrolką programu, takie jak źródło danych lub błędy we/wy sieci. Błędy, które mogą być widoczne w normalnym czasie wykonywania programu, zazwyczaj nie są uważane za wyjątki.

Możesz uzyskać dostęp do tych obiektów w zakresie wyrażenia **catch** . Możesz również generować `CDBException` obiekty z własnego kodu za pomocą `AfxThrowDBException` funkcji globalnej.

Aby uzyskać więcej informacji na temat obsługi wyjątków ogólnych lub o `CDBException` obiektach, zobacz [Obsługa wyjątków artykułów (MFC)](../../mfc/exception-handling-in-mfc.md) i [wyjątki: wyjątki bazy danych](../../mfc/exceptions-database-exceptions.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDB. h

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a> CDBException:: m_nRetCode

Zawiera kod błędu ODBC typu RETCODE zwracany przez funkcję interfejsu API ODBC.

### <a name="remarks"></a>Uwagi

Ten typ zawiera wstępnie ustalone kody zdefiniowane przez ODBC i AFX_SQL-z prefiksami zdefiniowanymi przez klasy baz danych. Dla programu `CDBException` , ten element członkowski będzie zawierać jedną z następujących wartości:

- AFX_SQL_ERROR_API_CONFORMANCE sterownik `CDatabase::OpenEx` lub `CDatabase::Open` wywołanie jest niezgodne z wymaganym poziomem zgodności interfejsu API ODBC 1 (SQL_OAC_LEVEL1).

- Nie można nawiązać połączenia AFX_SQL_ERROR_CONNECT_FAIL ze źródłem danych. Przeszedł wskaźnik o wartości NULL `CDatabase` do konstruktora zestawu rekordów i kolejną próbą utworzenia połączenia w oparciu o `GetDefaultConnect` Niepowodzenie.

- AFX_SQL_ERROR_DATA_TRUNCATED zażądano większej ilości danych niż podano w nim magazyn. Aby uzyskać informacje na temat zwiększania dostępnego magazynu danych `CString` lub `CByteArray` typów danych, zobacz `nMaxLength` argument dla [RFX_Text](record-field-exchange-functions.md#rfx_text) i [RFX_Binary](record-field-exchange-functions.md#rfx_binary) w obszarze "makra i Globals".

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED wywołanie `CRecordset::Open` żądania dynamicznego nie powiodło się. Zestawy dynamiczne nie są obsługiwane przez sterownik.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST podjęto próbę otwarcia tabeli (lub nie można zidentyfikować jej jako wywołania procedury lub instrukcji **SELECT** ), ale nie ma żadnych kolumn zidentyfikowanych w wywołaniach funkcji wymiany pól rekordów (RFX) w `DoFieldExchange` zastąpieniu.

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH typ funkcji RFX w `DoFieldExchange` przesłonięciu nie jest zgodny z typem danych kolumny w zestawie rekordów.

- AFX_SQL_ERROR_ILLEGAL_MODE wywołana `CRecordset::Update` bez uprzedniego wywołania metody `CRecordset::AddNew` lub `CRecordset::Edit` .

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED nie można spełnić żądania zablokowania rekordów dla aktualizacji, ponieważ sterownik ODBC nie obsługuje blokowania.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED wywołana `CRecordset::Update` lub `Delete` dla tabeli bez klucza unikatowego i nie zmieniono wielu rekordów.

- AFX_SQL_ERROR_NO_CURRENT_RECORD podjęto próbę edycji lub usunięcia wcześniej usuniętego rekordu. Po usunięciu należy przewinąć do nowego bieżącego rekordu.

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES nie można spełnić żądania dla elementu dynamicznego, ponieważ sterownik ODBC nie obsługuje aktualizacji pozycjonowanych.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED wywołana `CRecordset::Update` lub `Delete` , ale po rozpoczęciu operacji nie można już znaleźć rekordu.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED próba załadowania ODBC.DLL nie powiodła się; System Windows nie może odnaleźć lub nie może załadować tej biblioteki DLL. Ten błąd jest krytyczny.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED nie można spełnić żądania dla elementu dynamicznego, ponieważ wymagany jest sterownik ODBC zgodny ze standardem Level 2.

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY Próba przewinięcia nie powiodła się, ponieważ źródło danych nie obsługuje przewijania wstecznego.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED wywołanie `CRecordset::Open` żądania migawki nie powiodło się. Migawki nie są obsługiwane przez sterownik. (Powinno się to odbywać tylko wtedy, gdy biblioteka kursorów ODBC ODBCCURS.DLL nie istnieje).

- AFX_SQL_ERROR_SQL_CONFORMANCE sterownik `CDatabase::OpenEx` lub `CDatabase::Open` wywołanie jest niezgodne z wymaganym poziomem zgodności ODBC SQL "minimum" (SQL_OSC_MINIMUM).

- AFX_SQL_ERROR_SQL_NO_TOTAL sterownik ODBC nie mógł określić łącznego rozmiaru `CLongBinary` wartości danych. Operacja prawdopodobnie nie powiodła się, ponieważ nie można wstępnie przydzielyć globalnego bloku pamięci.

- AFX_SQL_ERROR_RECORDSET_READONLY próbowano zaktualizować zestaw rekordów tylko do odczytu lub źródło danych jest tylko do odczytu. Nie można wykonywać operacji aktualizacji z zestawem rekordów lub `CDatabase` obiektem, z którym jest skojarzony.

- Funkcja SQL_ERROR nie powiodła się. Komunikat o błędzie zwracany przez funkcję ODBC `SQLError` jest przechowywany w `m_strError` elemencie członkowskim danych.

- Funkcja SQL_INVALID_HANDLE nie powiodła się z powodu nieprawidłowego dojścia do środowiska, dojścia do połączenia lub dojście do instrukcji. Wskazuje to na błąd programowania. Funkcja ODBC nie udostępnia żadnych dodatkowych informacji `SQLError` .

Kody z prefiksem SQL są definiowane przez ODBC. Kody z prefiksem AFX są zdefiniowane w AFXDB. H, znaleziono w MFC\INCLUDE.

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a> CDBException:: m_strError

Zawiera ciąg opisujący błąd, który spowodował wyjątek.

### <a name="remarks"></a>Uwagi

Ciąg opisuje błąd w wyrażeniach alfanumerycznych. Aby uzyskać bardziej szczegółowe informacje i przykład, zobacz `m_strStateNativeOrigin` .

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a> CDBException:: m_strStateNativeOrigin

Zawiera ciąg opisujący błąd, który spowodował wyjątek.

### <a name="remarks"></a>Uwagi

Ciąg ma postać "State:% s, Native:% LD, Origin:% s", gdzie Kody formatu w kolejności są zastępowane przez wartości opisujące:

- SQLSTATE, ciąg zakończony znakiem null zawierający kod błędu pięciu znaków zwracany w parametrze *szSqlState* funkcji ODBC `SQLError` . Wartości SQLSTATE są wymienione w dodatku A, [kody błędów ODBC](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes), w *Kompendium ODBC programisty*. Przykład: "S0022".

- Kod błędu natywnego, charakterystyczny dla źródła danych, zwracany w parametrze *pfNativeError* `SQLError` funkcji. Przykład: 207.

- Tekst komunikatu o błędzie zwracany w parametrze *szErrorMsg* `SQLError` funkcji. Ten komunikat składa się z kilku nazw ujętych w nawiasy klamrowe. Ponieważ do użytkownika jest przesyłany błąd, każdy składnik ODBC (Źródło danych, Sterownik, Menedżer sterowników) dołącza własną nazwę. Te informacje ułatwiają określenie źródła błędu. Przykład: [Microsoft] [ODBC SQL Server Driver] [SQL Server]

Struktura interpretuje ciąg błędu i umieszcza jego składniki w `m_strStateNativeOrigin` ; Jeśli `m_strStateNativeOrigin` zawiera informacje dla więcej niż jednego błędu, błędy są rozdzielone znakami nowego wiersza. Struktura umieszcza alfanumeryczny tekst błędu w `m_strError` .

Aby uzyskać dodatkowe informacje na temat kodów używanych do przepełnienia tego ciągu, zobacz funkcję [SqlError](/sql/odbc/reference/syntax/sqlerror-function) w *dokumentacji programu ODBC programmer's Reference*.

### <a name="example"></a>Przykład

Z ODBC: "State: S0022, Native: 207, Origin: \[ Microsoft] \[ ODBC SQL Server Driver] \[ SQL Server] Nieprawidłowa nazwa kolumny" ColName ""

W `m_strStateNativeOrigin` : "State: S0022, Native: 207, Origin: \[ Microsoft] \[ ODBC SQL Server Driver] \[ SQL Server]"

W `m_strError` : "Nieprawidłowa nazwa kolumny" ColName ""

## <a name="see-also"></a>Zobacz też

[Klasa CException](../../mfc/reference/cexception-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Klasa CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Klasa CFieldExchange](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset:: Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::D Usuń](../../mfc/reference/crecordset-class.md#delete)<br/>
[Klasa CException](../../mfc/reference/cexception-class.md)
