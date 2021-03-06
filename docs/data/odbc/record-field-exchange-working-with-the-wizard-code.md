---
description: 'Dowiedz się więcej na temat: Wymiana pól rekordów: Praca z kodem kreatora'
title: 'Wymiana pól rekordów: praca z kodem kreatora'
ms.date: 05/09/2019
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
ms.openlocfilehash: c6b44c7c5e3ec09e02e70ad5dd0fecfa434cc0a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278717"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Wymiana pól rekordów: praca z kodem kreatora

> [!NOTE]
> Kreator użytkownika ODBC MFC nie jest dostępny w programie Visual Studio 2019 i nowszych. Nadal można utworzyć konsumenta ręcznie.

W tym temacie opisano kod, który Kreator aplikacji MFC i **Dodawanie klasy** (zgodnie z opisem w temacie [Dodawanie użytkownika MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) do obsługi RFX oraz jak można zmienić ten kod.

> [!NOTE]
> Ten temat dotyczy klas pochodnych `CRecordset` , w których nie zaimplementowano pobierania wierszy zbiorczych. W przypadku korzystania z pobierania wierszy zbiorczych zaimplementowano wymianę zbiorczych pól rekordów (bulk RFX). RFX Bulk jest podobna do RFX. Aby zrozumieć różnice, zobacz [zestaw rekordów: pobieranie rekordów zbiorczo (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Podczas tworzenia klasy zestawu rekordów przy użyciu Kreatora aplikacji MFC lub **dodawania klasy**, kreator zapisuje następujące elementy powiązane z RFXem na podstawie opcji źródła danych, tabeli i kolumny, które należy wykonać w Kreatorze:

- Deklaracje elementów członkowskich danych pola zestawu rekordów w klasie zestawu rekordów

- Zastąpienie elementu `CRecordset::DoFieldExchange`

- Inicjalizacja elementów członkowskich danych pola zestawu rekordów w konstruktorze klas zestawu rekordów

## <a name="field-data-member-declarations"></a><a name="_core_the_field_data_member_declarations"></a> Deklaracje elementu członkowskiego danych pola

Kreatorzy zapisują deklarację klasy zestawu rekordów w pliku h, który przypomina następujące klasy `CSections` :

```cpp
class CSections : public CRecordset
{
public:
   CSections(CDatabase* pDatabase = NULL);
   DECLARE_DYNAMIC(CSections)

// Field/Param Data
   CString   m_strCourseID;
   CString   m_strInstructorID;
   CString   m_strRoomNo;
   CString   m_strSchedule;
   CString   m_strSectionNo;

// Overrides
   // Wizard generated virtual function overrides
   protected:
   virtual CString GetDefaultConnect();  // Default connection string
   virtual CString GetDefaultSQL();      // Default SQL for Recordset
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support

// Implementation
#ifdef _DEBUG
   virtual void AssertValid() const;
   virtual void Dump(CDumpContext& dc) const;
#endif

};
```

Jeśli dodasz elementy członkowskie danych parametrów lub nowe elementy członkowskie danych pola, które utworzysz samodzielnie, Dodaj je po wygenerowanym przez kreatora.

Należy również zauważyć, że Kreator zastępuje `DoFieldExchange` funkcję składową klasy `CRecordset` .

## <a name="dofieldexchange-override"></a><a name="_core_the_dofieldexchange_override"></a> DoFieldExchange zastąpienie

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) to serce z RFX. Platforma wywołuje `DoFieldExchange` każdy czas potrzebny do przeniesienia danych ze źródła danych do zestawu rekordów lub z zestawu rekordów do źródła danych. `DoFieldExchange` Program obsługuje również uzyskiwanie informacji o elementach członkowskich danych pól za pomocą funkcji składowych [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) i [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) .

Poniższe `DoFieldExchange` przesłonięcie dotyczy `CSections` klasy. Kreator zapisuje funkcję w pliku CPP dla klasy zestawu rekordów.

```cpp
void CSections::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Text(pFX, "CourseID", m_strCourseID);
   RFX_Text(pFX, "InstructorID", m_strInstructorID);
   RFX_Text(pFX, "RoomNo", m_strRoomNo);
   RFX_Text(pFX, "Schedule", m_strSchedule);
   RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

Zwróć uwagę na następujące kluczowe funkcje funkcji:

- Ta sekcja funkcji jest nazywana mapą pól.

- Wywołanie do `CFieldExchange::SetFieldType` , za pomocą `pFX` wskaźnika. To wywołanie określa, że wszystkie funkcje RFX są wywoływane do końca `DoFieldExchange` lub następnego wywołania do `SetFieldType` są kolumnami wyjściowymi. Aby uzyskać więcej informacji, zobacz [CFieldExchange:: SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Kilka wywołań `RFX_Text` funkcji globalnej — jeden na każdy element członkowski danych (wszystkie są `CString` zmiennymi w przykładzie). Te wywołania określają relację między nazwą kolumny w źródle danych i elementem członkowskim danych pola. Funkcje RFX wykonują rzeczywisty transfer danych. Biblioteka klas udostępnia funkcje RFX dla wszystkich wspólnych typów danych. Aby uzyskać więcej informacji o funkcjach RFX, zobacz [wymiany pól rekordów: korzystanie z funkcji RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).

    > [!NOTE]
    >  Kolejność kolumn w zestawie wyników musi być zgodna z kolejnością wywołań funkcji RFX w `DoFieldExchange` .

- `pFX`Wskaźnik do obiektu [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) , który jest przekazywany przez platformę, gdy wywołuje `DoFieldExchange` . `CFieldExchange`Obiekt Określa operację `DoFieldExchange` , która ma zostać wykonana, kierunek transferu i inne informacje kontekstowe.

## <a name="recordset-constructor"></a><a name="_core_the_recordset_constructor"></a> Konstruktor zestawu rekordów

Konstruktor zestawu rekordów, który zapisuje kreatory, zawiera dwie rzeczy powiązane z RFX:

- Inicjalizacja dla każdego elementu członkowskiego danych pola

- Inicjalizacja elementu członkowskiego danych [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) , który zawiera liczbę elementów członkowskich danych pola

Konstruktor dla `CSections` przykładu zestawu rekordów wygląda następująco:

```cpp
CSections::CSections(CDatabase* pdb)
   : CRecordset(pdb)
{
   m_strCourseID = "";
   m_strInstructorID = "";
   m_strRoomNo = "";
   m_strSchedule = "";
   m_strSectionNo = "";
   m_nFields = 5;
}
```

> [!NOTE]
> Jeśli wszystkie elementy członkowskie danych pól są dodawane ręcznie, w miarę jak można dynamicznie powiązać nowe kolumny, należy zwiększyć wartość `m_nFields` . Zrób to, dołączając inny wiersz kodu, taki jak:

```cpp
m_nFields += 3;
```

Jest to kod służący do dodawania trzech nowych pól. W przypadku dodania dowolnego elementu członkowskiego danych, należy zainicjować element członkowski danych [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) zawierający liczbę elementów członkowskich danych parametru. Umieść `m_nParams` inicjalizację poza nawiasami.

## <a name="see-also"></a>Zobacz też

[Wymiana pól rekordów (RFX)](../../data/odbc/record-field-exchange-rfx.md)
