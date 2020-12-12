---
description: 'Dowiedz się więcej na temat: TN068: wykonywanie transakcji za pomocą sterownika Microsoft Access 7 ODBC'
title: 'TN068: wykonywanie transakcji za pomocą sterownika Microsoft Access 7 ODBC Driver'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: ebc98a0fd2bea78c0159daa9a53a11a292482257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214549"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: wykonywanie transakcji za pomocą sterownika Microsoft Access 7 ODBC Driver

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

W tej części opisano sposób wykonywania transakcji przy użyciu klas baz danych MFC ODBC oraz sterownika Microsoft Access 7,0 ODBC dołączonego do pakietu sterowników Microsoft ODBC Desktop w wersji 3,0.

## <a name="overview"></a>Omówienie

Jeśli aplikacja bazy danych wykonuje transakcje, należy zachować ostrożność w wywołaniu `CDatabase::BeginTrans` i `CRecordset::Open` w odpowiedniej kolejności w aplikacji. Sterownik Microsoft Access 7,0 korzysta z aparatu bazy danych Microsoft Jet, a aparat Jet wymaga, aby aplikacja nie rozpoczęła transakcji w żadnej bazie danych, która ma otwarty kursor. W przypadku klas baz danych MFC ODBC, otwarty kursor jest równe otwartemu `CRecordset` obiektowi.

Jeśli zestaw rekordów zostanie otwarty przed wywołaniem `BeginTrans` , mogą nie być wyświetlane żadne komunikaty o błędach. Jednak każdy zestaw rekordów aktualizuje aplikację, staje się trwała po wywołaniu `CRecordset::Update` , a aktualizacje nie zostaną wycofane przez wywołanie `Rollback` . Aby uniknąć tego problemu, należy najpierw wywołać metodę, `BeginTrans` a następnie otworzyć zestaw rekordów.

MFC sprawdza funkcjonalność sterownika dla zachowania zatwierdzania i wycofywania kursora. Klasa `CDatabase` udostępnia dwie funkcje członkowskie `GetCursorCommitBehavior` i `GetCursorRollbackBehavior` , aby określić efekt transakcji w otwartym `CRecordset` obiekcie. W przypadku sterownika ODBC programu Microsoft Access 7,0 te funkcje członkowskie zwracają, `SQL_CB_CLOSE` ponieważ sterownik dostępu nie obsługuje zachowywania kursora. W związku z tym, należy wywołać `CRecordset::Requery` `CommitTrans` działanie po `Rollback` operacji lub.

Gdy konieczne jest wykonanie wielu transakcji jeden po drugim, nie można wywołać `Requery` po pierwszej transakcji, a następnie rozpocząć kolejne. Musisz zamknąć zestaw rekordów przed następnym wywołaniem w celu `BeginTrans` spełnienia wymagań aparatu Jet. Ta Uwaga techniczna opisuje dwie metody obsługi tej sytuacji:

- Zamykanie zestawu rekordów po każdej `CommitTrans` `Rollback` operacji lub.

- Za pomocą funkcji ODBC API `SQLFreeStmt` .

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Zamykanie zestawu rekordów po każdej operacji CommitTrans lub wycofywania

Przed rozpoczęciem transakcji upewnij się, że obiekt zestawu rekordów jest zamknięty. Po wywołaniu `BeginTrans` należy wywołać `Open` funkcję członkowską zestawu rekordów. Zamknij zestaw rekordów bezpośrednio po wywołaniu `CommitTrans` lub `Rollback` . Należy zauważyć, że wielokrotne otwieranie i zamykanie zestawu rekordów może spowolnić działanie aplikacji.

## <a name="using-sqlfreestmt"></a>Korzystanie z SQLFreeStmt

Możesz również użyć funkcji ODBC API, `SQLFreeStmt` Aby jawnie zamknąć kursor po zakończeniu transakcji. Aby rozpocząć kolejną transakcję, wywołaj polecenie `BeginTrans` `CRecordset::Requery` . Podczas wywoływania należy `SQLFreeStmt` określić HSTMT zestawu rekordów jako pierwszy parametr, a *SQL_CLOSE* jako drugi parametr. Ta metoda jest szybsza niż zamykanie i otwieranie zestawu rekordów na początku każdej transakcji. Poniższy kod ilustruje sposób implementacji tej techniki:

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

// close the cursor
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

// start transaction 2
db.BeginTrans();
// now get the result set
rs.Requery();

// manipulate data

// end transaction 2
db.CommitTrans();

rs.Close();
db.Close();
```

Innym sposobem implementacji tej techniki jest zapisanie nowej funkcji, `RequeryWithBeginTrans` którą można wywołać, aby rozpocząć następną transakcję po zatwierdzeniu lub wycofaniu pierwszej z nich. Aby napisać taką funkcję, wykonaj następujące czynności:

1. Skopiuj kod `CRecordset::Requery( )` do nowej funkcji.

2. Dodaj następujący wiersz bezpośrednio po wywołaniu `SQLFreeStmt` :

   `m_pDatabase->BeginTrans( );`

Teraz można wywołać tę funkcję między każdą parą transakcji:

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> Nie należy używać tej techniki, jeśli trzeba zmienić zmienne elementu członkowskiego zestawu rekordów *m_strFilter* lub *m_strSort* między transakcjami. W takim przypadku należy zamknąć zestaw rekordów po każdej `CommitTrans` `Rollback` operacji lub.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
