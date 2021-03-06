---
description: 'Dowiedz się więcej o: zestaw rekordów: więcej informacji o aktualizacjach (ODBC)'
title: 'Zestaw rekordów: więcej informacji o aktualizacjach (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
ms.openlocfilehash: 9d125456189828d50f1fbfd4aece00a16790424f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304444"
---
# <a name="recordset-more-about-updates-odbc"></a>Zestaw rekordów: więcej informacji o aktualizacjach (ODBC)

Ten temat dotyczy klas MFC ODBC.

W tym temacie objaśniono:

- [Sposób, w jaki inne operacje, takie jak transakcje, wpływają na aktualizacje](#_core_how_transactions_affect_updates).

- [Aktualizacje i inni użytkownicy](#_core_your_updates_and_the_updates_of_other_users).

- [Więcej informacji o funkcjach aktualizowania i usuwania elementów członkowskich](#_core_more_about_update_and_delete).

> [!NOTE]
> Ten temat dotyczy obiektów pochodnych `CRecordset` , w których nie zaimplementowano pobierania wierszy zbiorczych. Jeśli zaimplementowano pobieranie wierszy zbiorczych, niektóre informacje nie są stosowane. Na przykład nie można wywołać `AddNew` `Edit` funkcji,, `Delete` i `Update` składowych. można jednak wykonać transakcje. Aby uzyskać więcej informacji na temat pobierania wierszy zbiorczych, zobacz [zestaw rekordów: pobieranie rekordów zbiorczo (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a> Jak inne operacje mają wpływ na aktualizacje

Na aktualizacje mają wpływ transakcje wprowadzone w momencie aktualizacji, zamykając zestaw rekordów przed ukończeniem transakcji i przewijając przed ukończeniem transakcji.

### <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a> Jak transakcje mają wpływ na aktualizacje

Po zrozumieniu `AddNew` , jak `Edit` i `Delete` pracy, ważne jest, aby zrozumieć, jak `BeginTrans` `CommitTrans` `Rollback` funkcje składowe [CDatabase](../../mfc/reference/cdatabase-class.md) działają z funkcjami aktualizacji [CRecordset](../../mfc/reference/crecordset-class.md).

Domyślnie program wywołuje `AddNew` i `Edit` ma wpływ na źródło danych natychmiast po wywołaniu `Update` . `Delete` wywołania zaczynają obowiązywać natychmiast. Można jednak ustanowić transakcję i wykonać partię takich wywołań. Aktualizacje nie są trwałe, dopóki nie zostaną zatwierdzone. Jeśli zmienisz zdanie, możesz wycofać transakcję zamiast jej zatwierdzania.

Aby uzyskać więcej informacji na temat transakcji, zobacz [Transaction (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a> Jak zamknięcie zestawu rekordów ma wpływ na aktualizacje

W przypadku zamknięcia zestawu rekordów lub skojarzonego z nim `CDatabase` obiektu, gdy transakcja jest w toku (nie wywołano [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) lub [CDatabase:: Rollback](../../mfc/reference/cdatabase-class.md#rollback)), transakcja zostanie wycofana automatycznie (chyba że zaplecze bazy danych jest aparatem bazy danych Microsoft Jet).

> [!CAUTION]
> W przypadku korzystania z aparatu bazy danych Microsoft Jet zamknięcie zestawu rekordów wewnątrz jawnej transakcji nie powoduje zwolnienia żadnego z wierszy, które zostały zmodyfikowane lub zablokowane, dopóki transakcja jawna nie zostanie zatwierdzona lub wycofana. Zaleca się, aby zawsze otwierać i zamykać zestawy rekordów wewnątrz lub na zewnątrz jawnej transakcji aparatu Jet.

### <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a> Jak przewijanie ma wpływ na aktualizacje

Gdy [zestaw rekordów: przewijanie (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) w zestawie rekordów, bufor edycji jest wypełniany każdym nowym rekordem bieżącym (poprzedni rekord nie jest przechowywany jako pierwszy). Przewijanie powoduje pominięcie poprzednio usuniętych rekordów. Jeśli przewiniesz po `AddNew` `Edit` wywołaniu lub nie wywołasz, `Update` `CommitTrans` lub `Rollback` po raz pierwszy, wszelkie zmiany zostaną utracone (bez ostrzeżenia użytkownika), ponieważ nowy rekord zostanie przeniesiony do buforu edycji. Bufor edycji jest wypełniony rekordem, w którym przewiniesz, przechowywany rekord jest zwolniony i nie ma żadnych zmian w źródle danych. Dotyczy to zarówno programu `AddNew` , jak i `Edit` .

## <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a> Aktualizacje i aktualizacje innych użytkowników

W przypadku aktualizowania danych przy użyciu zestawu rekordów aktualizacje wpływają na innych użytkowników. Podobnie aktualizacje innych użytkowników w okresie istnienia zestawu rekordów mają wpływ na użytkownika.

W środowisku wielodostępnym inni użytkownicy mogą otwierać zestawy rekordów zawierające niektóre z tych samych rekordów, które zostały wybrane w zestawie rekordów. Zmiany w rekordzie przed pobraniem zostaną odzwierciedlone w zestawie rekordów. Ze względu na to, że zestawy dynamiczne pobierają rekord po każdym przewinięciu do niego, zestawy dynamiczne odzwierciedlają zmiany przy każdym przewinięciu do rekordu. Migawki pobierają rekord po raz pierwszy, dlatego migawki odzwierciedlają tylko te zmiany, które wystąpiły przed pierwszym przewinięciem do rekordu.

Rekordy dodawane przez innych użytkowników po otwarciu zestawu rekordów nie są wyświetlane w zestawie rekordów, chyba że zostanie ponownie przeszukany. Jeśli zestaw rekordów jest dynamiczny, zmiany w istniejących rekordach przez innych użytkowników są wyświetlane w dynamicznym czasie podczas przewijania do rekordu, którego to dotyczy. Jeśli zestaw rekordów jest migawką, zmiany nie są wyświetlane, dopóki nie zostanie ponownie przestawiona migawka. Jeśli chcesz zobaczyć rekordy dodane lub usunięte przez innych użytkowników w migawce lub rekordy dodane przez innych użytkowników w zestawie dynamicznym, wywołaj [CRecordset:: Requery](../../mfc/reference/crecordset-class.md#requery) , aby skompilować zestaw rekordów. (Należy zauważyć, że usunięcia innych użytkowników są wyświetlane w ramach zestawu dynamicznego). Możesz również wywołać `Requery` , aby zobaczyć rekordy, które dodasz, ale nie widzisz żadnych usunięć.

> [!TIP]
> Aby wymusić buforowanie całej migawki jednocześnie, należy wywołać `MoveLast` ją natychmiast po otwarciu migawki. Następnie Wywołaj `MoveFirst` , aby rozpocząć pracę z rekordami. `MoveLast` jest równoznaczne z przewijaniem wszystkich rekordów, ale pobiera je wszystkie jednocześnie. Należy jednak pamiętać, że może to obniżyć wydajność i może nie być wymagana w przypadku niektórych sterowników.

Efekty aktualizacji innych użytkowników są podobne do ich efektów.

## <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a> Więcej informacji o aktualizacjach i usuwaniu

Ta sekcja zawiera dodatkowe informacje ułatwiające korzystanie z programu `Update` i `Delete` .

### <a name="update-success-and-failure"></a>Powodzenie i niepowodzenie aktualizacji

Jeśli `Update` się powiedzie, `AddNew` tryb lub zostanie `Edit` zakończony. Aby ponownie rozpocząć `AddNew` `Edit` tryb lub, wywołaj `AddNew` lub `Edit` .

Jeśli `Update` nie powiedzie się (zwraca wartość false lub zgłosi wyjątek), pozostanie w `AddNew` `Edit` trybie lub, w zależności od tego, która funkcja została wywołana jako Ostatnia. Następnie można wykonać jedną z następujących czynności:

- Zmodyfikuj element członkowski danych pola i spróbuj `Update` ponownie.

- Wywołaj `AddNew` , aby zresetować elementy członkowskie danych pola do wartości null, ustaw wartości elementów członkowskich danych pola, a następnie `Update` ponownie wywołaj.

- Wywołaj, `Edit` Aby ponownie załadować wartości, które znajdowały się w zestawie rekordów przed pierwszym wywołaniem `AddNew` lub `Edit` , ustaw wartości elementów członkowskich danych pola, a następnie `Update` ponownie wywołaj. Po pomyślnym `Update` wywołaniu (z wyjątkiem `AddNew` wywołania) elementy członkowskie danych pola zachowują nowe wartości.

- Wywołanie `Move` (łącznie `Move` z parametrem AFX_MOVE_REFRESH lub 0), które opróżnia wszelkie zmiany i kończą `AddNew` działanie dowolnego lub `Edit` trybu.

### <a name="update-and-delete"></a>Aktualizowanie i usuwanie

Ta sekcja dotyczy zarówno programu `Update` , jak i `Delete` .

W przypadku `Update` operacji lub należy `Delete` zaktualizować jeden i tylko jeden rekord. Ten rekord jest bieżącym rekordem, który odnosi się do wartości danych w polach zestawu rekordów. Jeśli z jakiegoś powodu nie ma lub nie dotyczy więcej rekordów, zgłaszany jest wyjątek zawierający jedną z następujących wartości **RETCODE** :

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

Kiedy te wyjątki są zgłaszane, pozostanie w `AddNew` stanie lub w `Edit` trakcie wywoływania `Update` lub `Delete` . Poniżej przedstawiono najczęstsze scenariusze, w których te wyjątki są widoczne. Najprawdopodobniej zobaczysz:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED w przypadku korzystania z trybu blokowania optymistycznego, a inny użytkownik zmodyfikował rekord w taki sposób, że program nie będzie mógł zidentyfikować poprawnego rekordu do aktualizacji lub usunięcia.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED, gdy aktualizowana tabela nie ma klucza podstawowego lub unikatowego indeksu i nie masz wystarczającej liczby kolumn w zestawie rekordów, aby jednoznacznie identyfikować wiersz tabeli.

## <a name="see-also"></a>Zobacz też

[Zestaw rekordów (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Zestaw rekordów: jak zestawy rekordów wybierają rekordy (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Wymiana pól rekordów (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Wyjątki: wyjątki bazy danych](../../mfc/exceptions-database-exceptions.md)
