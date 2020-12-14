---
description: 'Dowiedz się więcej na temat: TN045: obsługa MFC/bazy danych dla długich varchar/varbinary'
title: 'TN045: obsługa MFC-Database długich Varchar-Varbinary'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 4e19147ab5ca392307f331b12d3cf24eb5fcc06f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215186"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: obsługa MFC/bazy danych pod względem typu danych Varchar/Varbinary

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje sposób pobierania i wysyłania **SQL_LONGVARCHAR** ODBC oraz typów danych **SQL_LONGVARBINARY** przy użyciu klas baz danych MFC.

## <a name="overview-of-long-varcharvarbinary-support"></a>Omówienie długiej obsługi varchar/varbinary

**SQL_LONG_VARCHAR** ODBC i **SQL_LONGBINARY** typy danych (nazywane kolumnami danych długich) mogą zawierać ogromne ilości danych. Istnieją trzy sposoby obsługi tych danych:

- Powiąż go z `CString` / `CByteArray` .

- Powiąż go z `CLongBinary` .

- Nie należy wiązać go ze wszystkimi i pobierać i wysyłać wartości Long Data ręcznie niezależnie od klas baz danych.

Każda z tych trzech metod ma zalety i wady.

Kolumny danych długich nie są obsługiwane w przypadku parametrów do zapytania. Są one obsługiwane tylko w przypadku outputColumns.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Wiązanie kolumny danych long z CString/CByteArray

Zalety:

To podejście jest łatwe do zrozumienia i pracujesz z znanymi klasami. Struktura zapewnia `CFormView` obsługę programu dla `CString` programu `DDX_Text` . Istnieje wiele ogólnych funkcji ciągów lub kolekcji z `CString` `CByteArray` klasami i i można kontrolować ilość pamięci przydzieloną lokalnie w celu przechowywania wartości danych. Struktura zachowuje starą kopię danych pól w trakcie `Edit` lub `AddNew` wywołania funkcji, a platforma może automatycznie wykrywać zmiany w danych.

> [!NOTE]
> Ponieważ program `CString` został zaprojektowany do pracy nad danymi znakowymi i `CByteArray` do pracy z danymi binarnymi, zaleca się umieszczenie danych znakowych (**SQL_LONGVARCHAR**) w `CString` , a dane binarne (**SQL_LONGVARBINARY**) do `CByteArray` .

Funkcja RFX dla `CString` i `CByteArray` ma dodatkowy argument, który umożliwia przesłonięcie domyślnego rozmiaru przydzieloną pamięci, aby pomieścić pobraną wartość dla kolumny dane. Zwróć uwagę na argument nMaxLength w następujących deklaracjach funkcji:

```cpp
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

Jeśli pobrano kolumnę danych długich do `CString` lub `CByteArray` , maksymalna zwrócona ilość danych wynosi domyślnie 255 bajtów. Wszystkie elementy poza tym zostaną zignorowane. W takim przypadku platforma zgłosi wyjątek **AFX_SQL_ERROR_DATA_TRUNCATED**. Na szczęście można jawnie zwiększyć nMaxLength do większej liczby wartości, do **MAXINT**.

> [!NOTE]
> Wartość nMaxLength jest używana przez MFC do ustawiania buforu lokalnego `SQLBindColumn` funkcji. Jest to lokalny bufor do przechowywania danych i nie wpływa na ilość danych zwracanych przez sterownik ODBC. `RFX_Text` i nawiązać `RFX_Binary` tylko jedno wywołanie, `SQLFetch` Aby pobrać dane z bazy danych zaplecza. Każdy sterownik ODBC ma inne ograniczenie dotyczące ilości danych, które mogą zostać zwrócone w jednym pobieraniu. Ten limit może być znacznie mniejszy niż wartość ustawiona w nMaxLength, w którym to przypadku wyjątek **AFX_SQL_ERROR_DATA_TRUNCATED** zostanie wygenerowany. W tych okolicznościach Przełącz się do użycia `RFX_LongBinary` zamiast lub, aby `RFX_Text` można było `RFX_Binary` pobrać wszystkie dane.

ClassWizard powiąże **SQL_LONGVARCHAR** z `CString` lub **SQL_LONGVARBINARY** do `CByteArray` użytkownika. Jeśli chcesz przydzielić więcej niż 255 bajtów, w których pobierana jest kolumna danych długich, możesz podać wartość jawną dla nMaxLength.

Gdy kolumna danych long jest powiązana z `CString` lub `CByteArray` , aktualizacja pola działa tak samo, jak w przypadku powiązania z SQL_ **varchar** lub SQL_ **varbinary**. W czasie `Edit` , wartość danych jest buforowana i później porównywana, gdy `Update` jest wywoływana w celu wykrywania zmian wartości danych i odpowiednio ustawia wartości zanieczyszczone i wartości null dla kolumny.

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Wiązanie kolumny danych długich z CLongBinary

Jeśli kolumna danych długich może zawierać więcej **MAXINT** bajtów danych, prawdopodobnie należy rozważyć pobranie jej do `CLongBinary` .

Zalety:

Spowoduje to pobranie całej kolumny Long Data, do dostępnej pamięci.

Wady:

Dane są przechowywane w pamięci. To podejście jest również niezwykle drogie dla bardzo dużych ilości danych. Musisz wywołać `SetFieldDirty` dla powiązanego elementu członkowskiego danych, aby upewnić się, że pole jest uwzględniane w `Update` operacji.

W przypadku pobierania długich kolumn danych do programu `CLongBinary` , klasy baz danych będą sprawdzać łączny rozmiar kolumny Long Data, a następnie przydzielić `HGLOBAL` segment pamięci wystarczająco duży, aby pomieścić całą wartość danych. Klasy baz danych pobierają całą wartość danych do przydzielonej `HGLOBAL` .

Jeśli źródło danych nie może zwrócić oczekiwanego rozmiaru kolumny danych długich, platforma zgłosi wyjątek **AFX_SQL_ERROR_SQL_NO_TOTAL**. Jeśli próba przydzielenia `HGLOBAL` awarii nie powiedzie się, zostanie wygenerowany standardowy wyjątek pamięci.

ClassWizard będzie powiązać **SQL_LONGVARCHAR** lub **SQL_LONGVARBINARY** do `CLongBinary` użytkownika. Wybierz `CLongBinary` jako typ zmiennej w oknie dialogowym Dodawanie zmiennej składowej. ClassWizard następnie doda `RFX_LongBinary` wywołanie do `DoFieldExchange` wywołania i zwiększy łączną liczbę pól związanych.

Aby zaktualizować wartości kolumn długich danych, należy najpierw upewnić się, że przydzielone `HGLOBAL` jest wystarczająco duże, aby pomieścić nowe dane przez wywołanie **:: GlobalSize** na elemencie członkowskim *m_hData* `CLongBinary` . Jeśli jest za mały, zwolnij `HGLOBAL` i Przydziel jeden odpowiedni rozmiar. Następnie ustaw *m_dwDataLength* , aby odzwierciedlały nowy rozmiar.

W przeciwnym razie, jeśli wartość *m_dwDataLength* jest większa niż rozmiar danych, które są zastępowane, możesz ją zwolnić i ponownie przydzielić `HGLOBAL` lub pozostawić przydzieloną. Upewnij się, że podajesz liczbę bajtów rzeczywiście używanych w *m_dwDataLength*.

## <a name="how-updating-a-clongbinary-works"></a>Jak działa aktualizacja CLongBinary

Nie ma potrzeby zrozumienia sposobu aktualizowania programu `CLongBinary` Works, ale może być przydatne jako przykład wysyłania długich wartości danych do źródła danych, w przypadku wybrania tej trzeciej metody opisanej poniżej.

> [!NOTE]
> Aby `CLongBinary` pole było uwzględniane w aktualizacji, należy jawnie wywołać `SetFieldDirty` dla tego pola. Jeśli wprowadzisz jakiekolwiek zmiany do pola, w tym ustawienie jego wartości null, należy wywołać metodę `SetFieldDirty` . Należy również wywołać `SetFieldNull` , z drugim parametrem o wartości **false**, aby oznaczyć pole jako posiadające wartość.

Podczas aktualizowania `CLongBinary` pola klasy baz danych używają mechanizmu **DATA_AT_EXEC** ODBC (zobacz dokumentację ODBC na `SQLSetPos` rgbValue argument). Gdy struktura przygotowuje instrukcję INSERT lub Update, zamiast wskazywać na `HGLOBAL` zawierające dane, *adres* obiektu `CLongBinary` jest ustawiany jako *wartość* kolumny, a wskaźnik długości ustawiony na **SQL_DATA_AT_EXEC**. Później, gdy instrukcja UPDATE zostanie wysłana do źródła danych, `SQLExecDirect` zwróci **SQL_NEED_DATA**. Powoduje to wygenerowanie alertów, że wartość parametru param dla tej kolumny jest w rzeczywistości adresem `CLongBinary` . Struktura wywołuje `SQLGetData` jeden raz z małym buforem, co oczekuje, że sterownik zwróci rzeczywistą długość danych. Jeśli sterownik zwraca rzeczywistą długość dużego obiektu binarnego (obiektu BLOB), MFC przydziela tyle wolnego miejsca, aby pobrać obiekt BLOB. Jeśli źródło danych zwraca **SQL_NO_TOTAL**, wskazując, że nie można określić rozmiaru obiektu BLOB, MFC utworzy mniejsze bloki. Domyślny rozmiar początkowy to 64 KB, a kolejne bloki będą miały podwójny rozmiar; na przykład sekunda będzie 128K, trzecia jest 256 K i tak dalej. Rozmiar początkowy można skonfigurować.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Nie Powiąż: pobieranie/wysyłanie danych bezpośrednio z ODBC przy użyciu SQLGetData

Dzięki tej metodzie można całkowicie ominąć klasy baz danych i samodzielnie zajmować się kolumną Long Data.

Zalety:

W razie potrzeby można buforować dane na dysku, a także decydować o tym, jak dużo danych do pobrania.

Wady:

Nie otrzymujesz `Edit` ani nie `AddNew` obsługujesz struktury i musisz napisać kod samodzielnie, aby wykonać podstawowe funkcje ( `Delete` działa, ponieważ nie jest to operacja na poziomie kolumny).

W takim przypadku kolumna danych Long musi znajdować się na liście wyboru zestawu rekordów, ale nie powinna być powiązana z nią przez strukturę. Jednym ze sposobów wykonania tej czynności jest dostarczenie własnej instrukcji SQL za pośrednictwem `GetDefaultSQL` lub jako argumentu lpszSQL `CRecordset` do `Open` funkcji, a nie powiązanie dodatkowej kolumny z wywołaniem funkcji RFX_. ODBC wymaga, aby pola niepowiązane były wyświetlane z prawej strony pól powiązanych, dlatego Dodaj niepowiązaną kolumnę lub kolumny do końca listy wyboru.

> [!NOTE]
> Ponieważ kolumna danych długich nie jest powiązana z platformą, zmiany w niej nie będą obsługiwane w `CRecordset::Update` wywołaniach. Należy samodzielnie utworzyć i wysłać wymagane instrukcje **INSERT** i **Update** języka SQL.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
