---
description: 'Dowiedz się więcej o: zestaw rekordów: sortowanie rekordów (ODBC)'
title: 'Zestaw rekordów: sortowanie rekordów (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: fbf2ef3c42061bac9b41550a0c44a20f68c099b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204423"
---
# <a name="recordset-sorting-records-odbc"></a>Zestaw rekordów: sortowanie rekordów (ODBC)

Ten temat dotyczy klas MFC ODBC.

W tym temacie opisano sposób sortowania zestawu rekordów. Można określić co najmniej jedną kolumnę, na podstawie której ma zostać wykonane sortowanie, i można określić kolejność rosnącą lub malejącą (**ASC** lub **DESC**; Wartość **ASC** jest domyślna) dla każdej określonej kolumny. Na przykład w przypadku określenia dwóch kolumn rekordy są sortowane najpierw w pierwszej kolumnie o nazwie, a następnie w drugiej kolumnie o nazwie. Klauzula **order by** języka SQL definiuje sortowanie. Gdy struktura dołącza klauzulę **order by** do zapytania SQL zestawu rekordów, klauzula kontroluje kolejność zaznaczania.

Należy określić kolejność sortowania zestawu rekordów po utworzeniu obiektu, ale przed wywołaniem `Open` funkcji składowej (lub przed wywołaniem funkcji składowej `Requery` dla istniejącego obiektu zestawu rekordów, którego `Open` funkcja członkowska została wywołana wcześniej).

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Aby określić kolejność sortowania dla obiektu zestawu rekordów

1. Utwórz nowy obiekt zestawu rekordów (lub Przygotuj się do wywołania `Requery` istniejącej).

1. Ustaw wartość elementu członkowskiego danych [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) obiektu.

   Sortowanie jest ciągiem zakończonym wartością null. Zawiera zawartość klauzuli **order by** , ale nie słowo kluczowe **order by**. Możesz na przykład użyć następujących usług:

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. Ustaw inne potrzebne opcje, takie jak filtr, tryb blokowania lub parametry.

1. Wywołaj `Open` dla nowego obiektu (lub `Requery` dla istniejącego obiektu).

Wybrane rekordy są uporządkowane według określonych. Na przykład, aby posortować zestaw rekordów uczniów w kolejności malejącej według nazwiska, najpierw należy wykonać następujące czynności:

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

Zestaw rekordów zawiera wszystkie rekordy uczniów, posortowane w kolejności malejącej (od z do A) według nazwiska, a następnie według imienia i nazwiska.

> [!NOTE]
> Jeśli zdecydujesz się zastąpić domyślny ciąg SQL zestawu rekordów, przekazując własny ciąg SQL do `Open` , nie ustawiaj sortowania, jeśli niestandardowy ciąg ma klauzulę **order by** .

## <a name="see-also"></a>Zobacz też

[Zestaw rekordów (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Zestaw rekordów: parametryzacja a zestaw rekordów (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Zestaw rekordów: filtrowanie rekordów (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
