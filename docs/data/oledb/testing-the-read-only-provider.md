---
description: 'Dowiedz się więcej o: Testowanie dostawcy Read-Only'
title: Testowanie dostawcy tylko do odczytu
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: 2fbe0e7fb67b83cae65848939fa63bce42dab173
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272698"
---
# <a name="testing-the-read-only-provider"></a>Testowanie dostawcy tylko do odczytu

Do przetestowania dostawcy potrzebny jest klient. Pozwala to, aby klient mógł dopasować się do dostawcy. Szablony konsumentów OLE DB są cienkimi otokami wokół OLE DB i pasują do obiektów COM dostawcy. Ze względu na to, że źródło jest dostarczane z szablonami konsumentów, można łatwo debugować dostawcę z nimi. Szablony konsumentów są również bardzo niewielkim i szybkim sposobem tworzenia aplikacji dla użytkowników.

W przykładzie w tym temacie opisano tworzenie domyślnej aplikacji Kreatora aplikacji MFC dla konsumenta testowego. Aplikacja testowa to proste okno dialogowe z dodanym kodem szablonu klienta OLE DB.

## <a name="to-create-the-test-application"></a>Aby utworzyć aplikację testową

1. W menu **Plik** kliknij pozycję **Nowy**, a następnie kliknij pozycję **Projekt**.

1. W okienku **typy projektów** wybierz **zainstalowaną**  >  **Visual C++**  >  **MFC/ATL** . W okienku **Szablony** wybierz pozycję **aplikacja MFC**.

1. W polu Nazwa projektu wprowadź *TestProv*, a następnie kliknij przycisk **OK**.

   Zostanie wyświetlony Kreator **aplikacji MFC** .

1. Na stronie **Typ aplikacji** wybierz pozycję **okno dialogowe**.

1. Na stronie **funkcje zaawansowane** wybierz opcję **Automatyzacja**, a następnie kliknij przycisk **Zakończ**.

> [!NOTE]
> Aplikacja nie wymaga obsługi automatyzacji w przypadku dodania `CoInitialize` do programu `CTestProvApp::InitInstance` .

Możesz wyświetlić i edytować okno dialogowe **TestProv** (IDD_TESTPROV_DIALOG), wybierając je w **Widok zasobów**. Umieść dwa pola listy, jeden dla każdego ciągu w zestawie wierszy, w oknie dialogowym. Wyłącz Właściwość sortowania dla obu pól listy, naciskając klawisz **Alt** + **Enter** , gdy pole listy jest zaznaczone, i ustawiając właściwość **Sortuj** na **false**. Ponadto umieść przycisk **Run (Uruchom** ) w oknie dialogowym, aby pobrać plik. Okno dialogowe zakończono **TestProv** powinno mieć dwa pola listy z etykietą "String 1" i "String 2" odpowiednio; ma także przyciski **OK**, **Anuluj** i **Uruchom** .

Otwórz plik nagłówkowy dla klasy okna dialogowego (w tym przypadku TestProvDlg. h). Dodaj następujący kod do pliku nagłówkowego (poza dowolnymi deklaracjami klas):

```cpp
////////////////////////////////////////////////////////////////////////
// TestProvDlg.h
#include <atldbcli.h>  

class CProvider
{
// Attributes
public:
   char   szField1[16];
   char   szField2[16];

   // Binding Maps
BEGIN_COLUMN_MAP(CProvider)
   COLUMN_ENTRY(1, szField1)
   COLUMN_ENTRY(2, szField2)
END_COLUMN_MAP()
};
```

Kod reprezentuje rekord użytkownika, który definiuje, jakie kolumny będą znajdować się w zestawie wierszy. Gdy klient wywołuje `IAccessor::CreateAccessor` program, używa tych wpisów, aby określić, które kolumny mają być powiązane. Szablony konsumentów OLE DB umożliwiają również dynamiczne wiązanie kolumn. Makra COLUMN_ENTRY to wersja po stronie klienta PROVIDER_COLUMN_ENTRY makr. Dwa COLUMN_ENTRY makra określają numer porządkowy, typ, długość i składową danych dla dwóch ciągów.

Dodaj funkcję obsługi dla przycisku **Uruchom** , naciskając klawisz **Ctrl** i klikając dwukrotnie przycisk **Uruchom** . Umieść następujący kod w funkcji:

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession session;

   if (source.Open("Custom.Custom.1", NULL) != S_OK)
      return;

   if (session.Open(source) != S_OK)
      return;

   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)
      return;

   while (table.MoveNext() == S_OK)
   {
      m_ctlString1.AddString(table.szField1);
      m_ctlString2.AddString(table.szField2);
   }
}
```

`CCommand` `CDataSource` `CSession` Wszystkie klasy należą do OLE DB szablonów konsumentów. Każda Klasa śladuje obiekt COM w dostawcy. `CCommand`Obiekt przyjmuje `CProvider` klasę zadeklarowaną w pliku nagłówkowym jako parametr szablonu. `CProvider`Parametr reprezentuje powiązania, które są używane w celu uzyskania dostępu do danych od dostawcy.

Wiersze, aby otworzyć każdą z klas, tworzą każdy obiekt COM w dostawcy. Aby zlokalizować dostawcę, użyj `ProgID` dostawcy. Możesz uzyskać `ProgID` z rejestru systemowego lub w pliku Custom. RGS (Otwórz katalog dostawcy i wyszukać `ProgID` klucz).

Plik MyData.txt jest dołączony do `MyProv` przykładu. Aby utworzyć własny plik, użyj edytora i wpisz parzystą liczbę ciągów, naciskając klawisz **Enter** między każdym ciągiem. Zmień nazwę ścieżki, jeśli plik zostanie przeniesiony.

Przekaż ciąg "c: \\ \Samples \\ \myprov \\\MyData.txt" w `table.Open` wierszu. Jeśli przejdziesz do `Open` wywołania, zobaczysz, że ten ciąg jest przesyłany do `SetCommandText` metody w dostawcy. Należy zauważyć, że `ICommandText::Execute` Metoda używała tego ciągu.

Aby pobrać dane, wywołaj `MoveNext` tabelę. `MoveNext` wywołuje `IRowset::GetNextRows` funkcje, `GetRowCount` i `GetData` . Gdy nie ma więcej wierszy (czyli bieżąca pozycja w zestawie wierszy jest większa niż `GetRowCount` ), pętla kończy się.

Gdy nie ma więcej wierszy, dostawcy zwracają DB_S_ENDOFROWSET. Wartość DB_S_ENDOFROWSET nie jest błędem. Należy zawsze sprawdzać S_OK, aby anulować pętlę pobierania danych i nie używać pomyślnego makra.

Teraz powinno być możliwe skompilowanie i przetestowanie programu.

## <a name="see-also"></a>Zobacz też

[Ulepszanie prostego dostawcy Read-Only](../../data/oledb/enhancing-the-simple-read-only-provider.md)
