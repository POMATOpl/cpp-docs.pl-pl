---
description: 'Dowiedz się więcej o: TN043: RFX procedur'
title: 'TN043: procedury RFX'
ms.date: 06/28/2018
f1_keywords:
- RFX
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
ms.openlocfilehash: 6e5ac8271739e5cab80b79cb915b07e7d25622cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215225"
---
# <a name="tn043-rfx-routines"></a>TN043: procedury RFX

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje architekturę wymiany pól rekordów (RFX). Opisano w nim również sposób pisania procedury **RFX_ej** .

## <a name="overview-of-record-field-exchange"></a>Przegląd wymiany pól rekordów

Wszystkie funkcje pól zestawu rekordów są wykonywane przy użyciu kodu języka C++. Nie ma specjalnych zasobów ani magicznych makr. Sercem mechanizmu jest funkcja wirtualna, która musi zostać przesłonięta w każdej pochodnej klasie zestawu rekordów. Jest on zawsze znaleziony w tej postaci:

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

Specjalny format AFX komentarzy umożliwia ClassWizard do lokalizowania i edytowania kodu w ramach tej funkcji. Kod niezgodny z ClassWizard powinien być umieszczony poza specjalnymi komentarzami formatu.

W powyższym przykładzie \<recordset_exchange_field_type_call> ma postać:

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

i \<recordset_exchange_function_call> ma postać:

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

Większość funkcji **RFX_** ma trzy argumenty, jak pokazano powyżej, ale niektóre (np. `RFX_Text` i `RFX_Binary` ) mają dodatkowe argumenty opcjonalne.

Każda funkcja może zawierać więcej niż jeden **RFX_** `DoDataExchange` .

Aby uzyskać listę wszystkich procedur wymiany pól zestawu rekordów dostarczonych z MFC, zobacz "AFXDB. h".

Wywołania pola zestawu rekordów są sposobem rejestrowania lokalizacji pamięci (zazwyczaj składowych danych) do przechowywania danych pól dla `CMySet` klasy.

## <a name="notes"></a>Uwagi

Funkcje pól zestawu rekordów są przeznaczone do pracy tylko z `CRecordset` klasami. Nie są one ogólnie wykorzystywane przez żadną inną klasę MFC.

Początkowe wartości danych są ustawiane w standardowym konstruktorze języka C++, zazwyczaj w bloku z `//{{AFX_FIELD_INIT(CMylSet)` i `//}}AFX_FIELD_INIT` komentarzami.

Każda funkcja **RFX_** musi obsługiwać różne operacje, począwszy od zwrócenia stanu zanieczyszczonego pola w celu archiwizacji pola w celu edytowania pola.

Każda funkcja, która wywołuje `DoFieldExchange` (na `SetFieldNull` przykład `IsFieldDirty` ), ma swoje własne inicjalizacje wokół wywołania `DoFieldExchange` .

## <a name="how-does-it-work"></a>Jak to działa

Aby używać wymiany pól rekordów, nie trzeba zrozumieć następujących informacji. Jednak zrozumienie, jak to działa w tle, pomoże Ci napisać własną procedurę wymiany.

`DoFieldExchange`Funkcja członkowska jest podobnie jak `Serialize` funkcja członkowska — jest odpowiedzialna za pobieranie lub ustawianie danych do/z formularza zewnętrznego (w tym przypadku kolumny z wyniku zapytania ODBC) z/do danych elementu członkowskiego w klasie. Parametr *PFX* jest kontekstem do wykonywania wymiany danych i jest podobny do parametru *CArchive* do `CObject::Serialize` . *PFX* ( `CFieldExchange` obiekt) ma wskaźnik operacji, który jest podobny do, ale Generalizacja flagi kierunku *CArchive* . Funkcja RFX może być taka, aby obsługiwała następujące operacje:

- `BindParam` — Wskaż, gdzie ODBC ma pobierać dane parametrów

- `BindFieldToColumn` — Wskaż, gdzie ODBC musi pobierać/przelewać dane outputColumn

- `Fixup` — Ustawianie `CString/CByteArray` długości, Ustawianie bitu stanu o wartości null

- `MarkForAddNew` — Oznacz jako zanieczyszczone, jeśli wartość została zmieniona od wywołania metody AddNew

- `MarkForUpdate` — Oznacz jako zanieczyszczone, jeśli wartość została zmieniona od czasu wywołania edycji

- `Name` — Dołącz nazwy pól dla pól oznaczonych jako zanieczyszczone

- `NameValue` — Dołącz znak " \<column name> =" dla pól oznaczonych jako zanieczyszczone

- `Value` — Dołącz "", po którym następuje separator, taki jak "," lub ""

- `SetFieldDirty` — Ustaw bit stanu zanieczyszczony (tj. zmieniony) pole

- `SetFieldNull` — Ustaw bit stanu wskazujący wartość null dla pola

- `IsFieldDirty` — Wartość zwrócona przez bit stanu zanieczyszczonego

- `IsFieldNull` — Wartość zwrócona przez bit stanu o wartości null

- `IsFieldNullable` — Zwraca wartość PRAWDA, jeśli pole może zawierać wartości NULL

- `StoreField` — Wartość pola Archiwum

- `LoadField` — Załaduj ponownie zarchiwizowaną wartość pola

- `GetFieldInfoValue` — Zwraca ogólne informacje dotyczące pola

- `GetFieldInfoOrdinal` — Zwraca ogólne informacje dotyczące pola

## <a name="user-extensions"></a>Rozszerzenia użytkownika

Istnieje kilka sposobów, aby zwiększyć domyślny mechanizm RFX. Można

- Dodaj nowe typy danych. Na przykład:

    ```cpp
    CBookmark
    ```

- Dodaj nowe procedury wymiany (RFX_).

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- `DoFieldExchange`Funkcja członkowska warunkowo obejmuje dodatkowe wywołania RFX lub inne prawidłowe instrukcje języka C++.

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> Taki kod nie może być edytowany przez ClassWizard i powinien być używany tylko poza komentarzem w formacie specjalnym.

## <a name="writing-a-custom-rfx"></a>Pisanie niestandardowego RFX

Aby napisać własną niestandardową funkcję RFX, zaleca się skopiowanie istniejącej funkcji RFX i zmodyfikowanie jej do własnych celów. Wybranie odpowiedniej RFX do skopiowania może znacznie ułatwić wykonywanie zadań. Niektóre funkcje RFX mają unikatowe właściwości, które należy wziąć pod uwagę podczas podejmowania decyzji o kopiowaniu.

`RFX_Long` i `RFX_Int` : są to najprostsze funkcje RFX. Wartość danych nie wymaga żadnej specjalnej interpretacji, a rozmiar danych jest stały.

`RFX_Single` i `RFX_Double` : takie jak RFX_Long i RFX_Int powyżej, te funkcje są proste i mogą w szeroki sposób korzystać z implementacji domyślnej. Są one przechowywane w dbflt. cpp zamiast dbrfx. cpp, jednak aby włączyć ładowanie biblioteki zmiennoprzecinkowej środowiska uruchomieniowego tylko wtedy, gdy są one jawnie odwoływane.

`RFX_Text` i `RFX_Binary` : te dwie funkcje wstępnie przydzielą bufor statyczny do przechowywania informacji o ciągach/binarnych i muszą rejestrować te bufory przy użyciu ODBC SQLBindCol zamiast rejestrować wartość &. W związku z tym te dwie funkcje mają wiele specjalnych kodów wielkości liter.

`RFX_Date`: ODBC zwraca informacje o dacie i godzinie we własnej strukturze danych TIMESTAMP_STRUCT. Ta funkcja dynamicznie przydziela TIMESTAMP_STRUCT jako "serwer proxy" do wysyłania i otrzymywania danych daty i godziny. Różne operacje muszą przenosić informacje o dacie i godzinie między `CTime` obiektem C++ a serwerem proxy TIMESTAMP_STRUCT. To znacznie komplikuje tę funkcję, ale jest dobrym przykładem użycia serwera proxy do transferu danych.

`RFX_LongBinary`: Jest to jedyna funkcja RFX biblioteki klas, która nie używa powiązania kolumn do odbierania i wysyłania danych. Ta funkcja ignoruje operację BindFieldToColumn, a zamiast tego podczas operacji naprawy przydziela magazyn do przechowywania SQL_LONGVARCHAR przychodzących lub SQL_LONGVARBINARY danych, a następnie wykonuje wywołanie SQLGetData w celu pobrania wartości do przydzielonego magazynu. Podczas przygotowywania do wysyłania wartości danych z powrotem do źródła danych (np. operacji wartości nazwy i wartości) Ta funkcja używa DATA_AT_EXEC funkcji ODBC. Aby uzyskać więcej informacji na temat pracy z SQL_LONGVARBINARY i SQL_LONGVARCHARs, zobacz [Uwagi techniczne 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) .

Podczas pisania własnej funkcji **RFX_** często będzie można użyć `CFieldExchange::Default` do zaimplementowania danej operacji. Zapoznaj się z implementacją wartości domyślnej dla danej operacji. Jeśli wykonuje operację, którą można napisać w funkcji **RFX_** , można delegować do obiektu `CFieldExchange::Default` . Przykłady wywoływania można znaleźć `CFieldExchange::Default` w dbrfx. cpp

Ważne jest, aby wywołać `IsFieldType` na początku funkcji RFX i zwrócić natychmiast, jeśli zwróci wartość false. Ten mechanizm utrzymuje wykonywanie operacji na *outputColumns* i na odwrót (na przykład wywołując `BindParam` na *outputColumn*). Ponadto program `IsFieldType` automatycznie śledzi liczbę *outputColumns* (*m_nFields*) i params (*m_nParams*).

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
