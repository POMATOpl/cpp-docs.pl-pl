---
description: 'Dowiedz się więcej o: Transaction: wykonywanie transakcji w zestawie rekordów (ODBC)'
title: 'Transakcja: wykonywanie transakcji w zestawie rekordów (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: bb041d35e7ab0bfc7e19f2658a8cdadae4bd8c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333882"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Transakcja: wykonywanie transakcji w zestawie rekordów (ODBC)

W tym temacie wyjaśniono, jak wykonać transakcję w zestawie rekordów.

> [!NOTE]
> Obsługiwany jest tylko jeden poziom transakcji; nie można zagnieżdżać transakcji.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Aby wykonać transakcję w zestawie rekordów

1. Wywołaj `CDatabase` `BeginTrans` funkcję członkowską obiektu.

1. Jeśli nie zaimplementowano pobierania wierszy zbiorczych, wywołaj `AddNew/Update` `Edit/Update` funkcje, i `Delete` składowe co najmniej jednego obiektu zestawu rekordów w tej samej bazie danych tyle razy, ile jest to konieczne. Aby uzyskać więcej informacji, zobacz [zestaw rekordów: Dodawanie, aktualizowanie i usuwanie rekordów (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Jeśli zaimplementowano pobieranie wierszy zbiorczych, należy napisać własne funkcje, aby zaktualizować źródło danych.

1. Na koniec Wywołaj `CDatabase` `CommitTrans` funkcję członkowską obiektu. Jeśli w jednej z aktualizacji wystąpi błąd lub zdecydujesz się anulować zmiany, wywołaj jego `Rollback` funkcję członkowską.

W poniższym przykładzie zastosowano dwa zestawy rekordów, aby usunąć rejestrację ucznia z bazy danych rejestracji szkoły, usuwając uczniów ze wszystkich klas, w których student jest zarejestrowany. Ponieważ `Delete` wywołania w obu zestawach rekordów muszą się zakończyć pomyślnie, wymagana jest transakcja. W przykładzie przyjęto, że `m_dbStudentReg` zmienna elementu członkowskiego typu jest `CDatabase` już połączona ze źródłem danych, a klasy zestawu rekordów `CEnrollmentSet` i `CStudentSet` . `strStudentID`Zmienna zawiera wartość uzyskaną od użytkownika.

```
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )
{
    // remove student from all the classes
    // the student is enrolled in

    if ( !m_dbStudentReg.BeginTrans( ) )
        return FALSE;

    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )
        return FALSE;

    CStudentSet rsStudentSet(&m_dbStudentReg);
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsStudentSet.Open(CRecordset::dynaset) )
        return FALSE;

    TRY
    {
        while ( !rsEnrollmentSet.IsEOF( ) )
        {
            rsEnrollmentSet.Delete( );
            rsEnrollmentSet.MoveNext( );
        }

        // delete the student record
        rsStudentSet.Delete( );

        m_dbStudentReg.CommitTrans( );
    }

    CATCH_ALL(e)
    {
        m_dbStudentReg.Rollback( );
        return FALSE;
    }
    END_CATCH_ALL

    rsEnrollmentSet.Close( );
    rsStudentSet.Close( );

    return TRUE;

}
```

> [!NOTE]
> Wywoływanie `BeginTrans` ponownie bez wywoływania `CommitTrans` lub `Rollback` jest błędem.

## <a name="see-also"></a>Zobacz też

[Transakcja (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Transakcja: jak transakcje wpływają na aktualizacje (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[Klasa CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Klasa CRecordset](../../mfc/reference/crecordset-class.md)
