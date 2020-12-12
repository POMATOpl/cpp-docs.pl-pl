---
description: 'Dowiedz się więcej na temat: Obsługa bazy danych, Kreator aplikacji MFC'
title: Obsługa bazy danych, kreator aplikacji MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.database
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
ms.openlocfilehash: 4c6f980155e980c772b5ee78f83c80a236998b91
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220308"
---
# <a name="database-support-mfc-application-wizard"></a>Obsługa bazy danych, kreator aplikacji MFC

Ta strona zawiera opcje, które umożliwiają określenie poziomu obsługi bazy danych (oraz źródła danych, w razie potrzeby) dla projektu.

- **Obsługa bazy danych**

   Ustawia poziom obsługi bazy danych dla projektu.

   |Opcja|Opis|
   |------------|-----------------|
   |**Brak**|Nie zapewnia obsługi bazy danych. Jest to domyślne ustawienie opcji.|
   |**Tylko pliki nagłówkowe**|Zapewnia podstawowy poziom obsługi bazy danych dla aplikacji. W przypadku wybrania opcji obsługa ODBC w obszarze **Typ klienta** Kreator aplikacji MFC dołącza do projektu plik nagłówka AFXDB. H. Dodaje biblioteki łączy, ale nie tworzy żadnych klas specyficznych dla bazy danych. Zestawy rekordów można tworzyć później i używać ich do badania i aktualizowania rekordów. W przypadku wybrania opcji obsługa OLE DB w obszarze **Typ klienta** zostaną uwzględnione następujące pliki NAGŁÓWKOWE: atlbase. H AFXOLEDB. H ATLPLUS. C|
   |**Widok bazy danych bez obsługi plików**|Obejmuje pliki nagłówka bazy danych, biblioteki linków, widok rekordów i zestaw rekordów. (Dostępne tylko dla aplikacji z opcją **Obsługa architektura dokumentu/widoku** wybraną na stronie [Typ aplikacji](../../mfc/reference/application-type-mfc-application-wizard.md) ). Ta opcja obejmuje obsługę dokumentów, ale nie obsługuje serializacji. Jeśli wybierzesz opcję dołączenia widoku bazy danych, musisz określić źródło danych.|
   |**Widok bazy danych z obsługą plików**|Obejmuje pliki nagłówka bazy danych, biblioteki linków, widok rekordów i zestaw rekordów. (Dostępne tylko dla aplikacji z opcją **Obsługa architektura dokumentu/widoku** wybraną na stronie **Typ aplikacji** ). Ta opcja obsługuje serializację dokumentu, którego można użyć na przykład w celu zaktualizowania pliku profilu użytkownika. Aplikacje bazy danych zwykle działają dla poszczególnych rekordów, a nie na podstawie poszczególnych plików, a więc nie wymagają serializacji. Możliwe jest jednak użycie specjalnego użycia do serializacji. Jeśli wybierzesz opcję dołączenia widoku bazy danych, musisz określić źródło danych.|

   > [!NOTE]
   > W obszarze **Obsługa bazy danych** w przypadku wybrania opcji **Widok bazy danych bez obsługi plików** lub **widoku bazy danych z obsługą plików** wyprowadzenie klasy widoku różni się w zależności od wybranego **typu klienta** w następujący sposób:

  - Jeśli wybierzesz pozycję **ODBC** w obszarze **Typ klienta**, Klasa widoku aplikacji pochodzi od [formularzy CRecordView](../../mfc/reference/crecordview-class.md). Ta klasa jest skojarzona z klasą pochodną [CRecordset](../../mfc/reference/crecordset-class.md), którą tworzy również Kreator aplikacji MFC. Ta opcja zapewnia aplikację opartą na formularzach, w której widok rekordu służy do wyświetlania i aktualizowania rekordów za pośrednictwem jego zestawu rekordów.

  - W przypadku wybrania **OLE DB** w obszarze **Typ klienta** Klasa widoku pochodzi od [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)i jest skojarzona z klasą pochodną [CTable](../../data/oledb/ctable-class.md) lub [CCommand](../../data/oledb/ccommand-class.md).

- **Typ klienta**

   Wskazuje, czy projekt używa klas OLE DB czy ODBC.

   |Opcja|Opis|
   |------------|-----------------|
   |**OLE DB**|Gdy ta opcja jest zaznaczona, kliknięcie przycisku **Źródło danych** powoduje wywołanie kreatora **Właściwości łącza danych** w celu ułatwienia tworzenia połączenia ze źródłem danych OLE DB.|
   |**ODBC**|Po wybraniu tej opcji kliknięcie przycisku **Źródło danych** wywoła kreatora **wyboru źródła danych** , aby ułatwić utworzenie połączenia ze źródłem danych ODBC.|

- **Źródło danych**

   > [!NOTE]
   > Kreator użytkownika ATL OLE DB i Kreator użytkownika MFC ODBC nie są dostępne w programie Visual Studio 2019 i nowszych. Można nadal ręcznie dodawać funkcje. Aby uzyskać więcej informacji, zobacz [Tworzenie klienta bez korzystania z Kreatora](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

   Kliknij przycisk **źródła danych** , aby skonfigurować źródło danych przy użyciu określonego sterownika lub dostawcy i bazy danych. W przypadku wybrania opcji OLE DB w polu **Typ klienta** na tym przycisku zostanie wyświetlone okno dialogowe **Właściwości łącza danych** . Jeśli w opcji **Typ klienta** wybrano opcję ODBC, ten przycisk zapewnia okno dialogowe **Wybieranie źródła danych** . Ta opcja jest dostępna tylko wtedy, gdy użytkownik zdecyduje się na dołączenie widoku bazy danych do aplikacji.

   |Opcja|Opis|
   |------------|-----------------|
   |**Właściwości linku danych** (OLE DB)|Ustanawia określone źródło danych przy użyciu określonego dostawcy OLE DB. Należy określić dostawcę OLE DB, lokalizację danych, źródło danych, identyfikator logowania i (opcjonalnie) hasło. Aby uzyskać szczegółowe informacje na temat tego okna dialogowego, zobacz **Źródło danych** w [Kreatorze ATL OLE DB klienta](../../atl/reference/atl-ole-db-consumer-wizard.md).|
   |**Wybieranie źródła danych** (ODBC)|Ustanawia określone źródło danych przy użyciu określonego sterownika ODBC. Musisz wybrać nazwę źródła danych, aby wybrać tabelę dla źródła danych. Kreator powiąże wszystkie kolumny tabeli ze zmiennymi składowymi `CRecordset` klasy pochodnej. Aby uzyskać szczegółowe informacje na temat tego okna dialogowego, zobacz **Źródło danych** w [Kreatorze interfejsu użytkownika MFC ODBC](../../mfc/reference/mfc-odbc-consumer-wizard.md).|

- **Generuj klasę bazy danych z atrybutami**

   Dostępne tylko dla OLE DB klienta. Określa, czy klasy bazy danych w wygenerowanym projekcie używają atrybutów.

- **Powiąż wszystkie kolumny**

   Dostępne tylko dla klienta ODBC. Określa, czy wszystkie kolumny w zaznaczonej tabeli są powiązane. Jeśli zaznaczysz to pole, wszystkie kolumny są powiązane; Jeśli to pole nie zostanie zaznaczone, nie są powiązane żadne kolumny i musisz powiązać je ręcznie z klasą zestawów rekordów.

- **Typ**

   Dostępne tylko dla klienta ODBC. Określa, czy zestaw rekordów jest typu dynamicznego czy migawki, zgodnie z opisem w poniższej tabeli.

   |Opcja|Opis|
   |------------|-----------------|
   |**Zestaw dynamiczny**|Określa, że zestaw rekordów jest dynamiczny. Dynamiczny jest wynikiem zapytania, które zawiera indeksowany widok do danych zapytania bazy danych. Zestaw dynamiczny pamięci podręcznej tworzy tylko integralny indeks danych oryginalnych i w ten sposób oferuje wzrost wydajności dla migawki. Indeks wskazuje bezpośrednio na każdy rekord znaleziony w wyniku zapytania i wskazuje, czy rekord został usunięty. Masz również dostęp do zaktualizowanych informacji w rekordach zapytań.|
   |**Zdjęcie**|Określa, że zestaw rekordów jest migawką. Migawka jest wynikiem zapytania i jest widokiem w bazie danych w jednym punkcie czasu. Wszystkie rekordy Znalezione w wyniku zapytania są buforowane, więc nie są widoczne żadne zmiany w oryginalnych rekordach.|

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](../../mfc/reference/mfc-application-wizard.md)
