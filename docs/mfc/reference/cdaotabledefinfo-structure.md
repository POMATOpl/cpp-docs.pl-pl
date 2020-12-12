---
description: Dowiedz się więcej o strukturze CDaoTableDefInfo —
title: CDaoTableDefInfo — Struktura
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 953a255b35860dcce0ac8d3ef5081951dd15c344
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247973"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo — Struktura

`CDaoTableDefInfo`Struktura zawiera informacje o obiekcie tabledef zdefiniowanym dla obiektów dostępu do danych (DAO).

## <a name="syntax"></a>Składnia

```
struct CDaoTableDefInfo
{
    CString m_strName;               // Primary
    BOOL m_bUpdatable;               // Primary
    long m_lAttributes;              // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    CString m_strSrcTableName;       // Secondary
    CString m_strConnect;            // Secondary
    CString m_strValidationRule;     // All
    CString m_strValidationText;     // All
    long m_lRecordCount;             // All
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu tabledef. Aby bezpośrednio pobrać wartość tej właściwości, wywołaj funkcję członkowską [GetName](../../mfc/reference/cdaotabledef-class.md#getname) obiektu tabledef. Aby uzyskać więcej informacji, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_bUpdatable*<br/>
Wskazuje, czy można wprowadzać zmiany w tabeli. Szybka metoda określania, czy tabela jest aktualizowalna, to otwarcie `CDaoTableDef` obiektu dla tabeli i wywołanie funkcji elementu członkowskiego [aktualizacji](../../mfc/reference/cdaotabledef-class.md#canupdate) obiektu. `CanUpdate` zawsze zwraca wartość różną od zera (TRUE) dla nowo utworzonego obiektu tabledef i 0 (FALSE) dla dołączonego obiektu tabledef. Nowy obiekt tabledef może być dołączany tylko do bazy danych, dla której bieżący użytkownik ma uprawnienia do zapisu. Jeśli tabela zawiera tylko pola nieaktualizowalne, `CanUpdate` zwraca wartość 0. Gdy co najmniej jedno pole jest aktualizowalne, `CanUpdate` zwraca wartość różną od zera. Można edytować tylko pola aktualizowalne. Aby uzyskać więcej informacji, zobacz temat "Aktualizowalna właściwość" w pomocy DAO.

*m_lAttributes*<br/>
Określa charakterystykę tabeli reprezentowanej przez obiekt tabledef. Aby pobrać bieżące atrybuty elementu tabledef, wywołaj jego funkcję członkowską [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) . Zwracana wartość może być kombinacją tych długich stałych (przy użyciu operatora bitowego lub (**&#124;**)):

- `dbAttachExclusive` W przypadku baz danych korzystających z aparatu bazy danych Microsoft Jet wskazuje, że tabela jest dołączoną tabelą otwartą do wyłącznego użytku.

- `dbAttachSavePWD` W przypadku baz danych korzystających z aparatu bazy danych Microsoft Jet wskazuje, że identyfikator użytkownika i hasło do dołączonej tabeli są zapisywane wraz z informacjami o połączeniu.

- `dbSystemObject` Wskazuje, że tabela jest tabelą systemową dostarczoną przez aparat bazy danych Microsoft Jet. (Tylko do odczytu).

- `dbHiddenObject` Wskazuje, że tabela jest ukrytą tabelą dostarczoną przez aparat bazy danych Microsoft Jet (do tymczasowego użytku). (Tylko do odczytu).

- `dbAttachedTable` Wskazuje, że tabela jest dołączoną tabelą z bazy danych innej niż ODBC, takiej jak baza danych programu Paradox.

- `dbAttachedODBC` Wskazuje, że tabela jest dołączoną tabelą z bazy danych ODBC, takiej jak Microsoft SQL Server.

*m_dateCreated*<br/>
Data i godzina utworzenia tabeli. Aby bezpośrednio pobrać datę utworzenia tabeli, wywołaj funkcję członkowską [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) `CDaoTableDef` obiektu skojarzonego z tabelą. Aby uzyskać więcej informacji, zobacz poniższe komentarze. Aby uzyskać powiązane informacje, zobacz temat "DateCreated, LastUpdated Properties" w pomocy DAO.

*m_dateLastUpdated*<br/>
Data i godzina ostatniej zmiany dokonanej w projekcie tabeli. Aby bezpośrednio pobrać datę ostatniej aktualizacji tabeli, wywołaj funkcję członkowską [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) `CDaoTableDef` obiektu skojarzonego z tabelą. Aby uzyskać więcej informacji, zobacz poniższe komentarze. Aby uzyskać powiązane informacje, zobacz temat "DateCreated, LastUpdated Properties" w pomocy DAO.

*m_strSrcTableName*<br/>
Określa nazwę dołączonej tabeli, jeśli istnieje. Aby bezpośrednio pobrać nazwę tabeli źródłowej, wywołaj [](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) funkcję elementu członkowskiego GetSourceTableName `CDaoTableDef` obiektu skojarzonego z tabelą.

*m_strConnect*<br/>
Zawiera informacje o źródle otwartej bazy danych. Tę właściwość można sprawdzić, wywołując funkcję elementu członkowskiego [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) `CDaoTableDef` obiektu. Aby uzyskać więcej informacji na temat łączenia ciągów, zobacz `GetConnect` .

*m_strValidationRule*<br/>
Wartość, która weryfikuje dane w polach tabledef, gdy są one zmieniane lub dodawane do tabeli. Walidacja jest obsługiwana tylko w przypadku baz danych korzystających z aparatu bazy danych Microsoft Jet. Aby bezpośrednio pobrać regułę walidacji, wywołaj funkcję elementu członkowskiego [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) `CDaoTableDef` obiektu skojarzonego z tabelą. Aby uzyskać powiązane informacje, zobacz temat "Właściwość ValidationRule" w pomocy DAO.

*m_strValidationText*<br/>
Wartość określająca tekst komunikatu, który powinien być wyświetlany w aplikacji, jeśli reguła sprawdzania poprawności określona przez Właściwość ValidationRule nie jest spełniony. Aby uzyskać powiązane informacje, zobacz temat "Właściwość ValidationText" w pomocy DAO.

*m_lRecordCount*<br/>
Liczba rekordów, do których można uzyskać dostęp w obiekcie tabledef. To ustawienie właściwości jest tylko do odczytu. Aby bezpośrednio pobrać liczbę rekordów, wywołaj funkcję elementu członkowskiego [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) `CDaoTableDef` obiektu. W dokumentacji `GetRecordCount` opisano więcej rekordów. Należy pamiętać, że pobranie tej liczby może być czasochłonną operacją, jeśli tabela zawiera wiele rekordów.

## <a name="remarks"></a>Uwagi

Tabledef jest obiektem klasy [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Odwołania do elementów podstawowych, pomocniczych i wszystkie powyżej wskazują, jak informacje są zwracane przez funkcję składową [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) w klasie `CDaoDatabase` .

Informacje pobierane przez funkcję członkowską [CDaoDatabase:: GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) są przechowywane w `CDaoTableDefInfo` strukturze. Wywołaj `GetTableDefInfo` funkcję członkowską `CDaoDatabase` obiektu, w którym znajduje się TableDefs obiekt tabledef. `CDaoTableDefInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoTableDefInfo` obiektu.

Ustawienia daty i godziny są wyprowadzane z komputera, na którym utworzono lub ostatnio Zaktualizowano tabelę bazową. W środowisku wielodostępnym użytkownicy powinni uzyskać te ustawienia bezpośrednio z serwera plików, aby uniknąć rozbieżności w ustawieniach właściwości DateCreated i LastUpdated.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Klasa CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Klasa CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
