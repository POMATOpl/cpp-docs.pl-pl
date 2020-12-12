---
description: 'Dowiedz się więcej o: Sekwencja operacji tworzenia aplikacji bazy danych'
title: Sekwencja operacji przy tworzeniu aplikacji bazy danych
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: 86f06ae5200fc8646ccb80bfec4e2814b94f9225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217591"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Sekwencja operacji przy tworzeniu aplikacji bazy danych

W poniższej tabeli przedstawiono rolę i rolę platformy w pisaniu aplikacji baz danych.

> [!NOTE]
> Visual C++ środowisko i kreatorzy nie obsługują obiektów DAO (chociaż klasy DAO są dołączone i nadal można z nich korzystać). Firma Microsoft zaleca używanie ODBC w przypadku nowych projektów MFC. Obiektów DAO należy używać tylko w przypadku zarządzania istniejącymi aplikacjami.

### <a name="creating-database-applications"></a>Tworzenie aplikacji bazy danych

|Zadanie|Masz|Struktura wykonuje|
|----------|------------|------------------------|
|Zdecyduj, czy używać klas MFC ODBC czy DAO.|Użyj ODBC dla nowych projektów MFC. Używaj tylko DAO, aby obsługiwać istniejące aplikacje. Ogólne informacje znajdują się w artykule [Programowanie dostępu do danych](../data/data-access-programming-mfc-atl.md).|Struktura dostarcza klasy, które obsługują dostęp do bazy danych.|
|Utwórz aplikację szkieletową z opcjami bazy danych.|Uruchom Kreatora aplikacji MFC. Na stronie obsługa bazy danych wybierz opcje. W przypadku wybrania opcji, która tworzy widok rekordu, należy również określić:<br /><br />-Źródło danych i nazwa tabeli lub nazwy<br />-Nazwa zapytania lub nazwy.|Kreator aplikacji MFC tworzy pliki i określa niezbędne dołączenia. W zależności od określonych opcji pliki mogą zawierać klasę zestawu rekordów.|
|Zaprojektuj formularz lub formularze bazy danych.|Użyj edytora okien dialogowych Visual C++ do umieszczania kontrolek w zasobach szablonu okna dialogowego dla klas widoku rekordu.|Kreator aplikacji MFC tworzy pusty zasób szablonu okna dialogowego do wypełnienia.|
|Utwórz dodatkowy widok rekordu i klasy zestawu rekordów w razie konieczności.|Użyj Widok klasy, aby utworzyć klasy i Edytor okien dialogowych, aby zaprojektować widoki.|Widok klasy tworzy dodatkowe pliki dla nowych klas.|
|Utwórz obiekty zestawu rekordów zgodnie z potrzebami w kodzie. Użyj każdego zestawu rekordów do manipulowania rekordami...|Zestawy rekordów są oparte na klasach pochodzących od [CRecordset](../mfc/reference/crecordset-class.md) za pomocą kreatorów.|ODBC używa wymiany pól rekordów (RFX) do wymiany danych między bazą danych a elementami członkowskimi danych pola zestawu rekordów. W przypadku korzystania z widoku rekordu usługa wymiany danych (DDX) wymienia dane między zestawem rekordów i kontrolkami w widoku rekordu.|
|... lub Utwórz jawną [CDatabase](../mfc/reference/cdatabase-class.md) w kodzie dla każdej bazy danych, którą chcesz otworzyć.|Oparcie obiektów zestawu rekordów w obiektach bazy danych.|Obiekt bazy danych udostępnia interfejs do źródła danych.|
|Dynamiczne powiązanie kolumn danych z zestawem rekordów.|W programie ODBC Dodaj kod do klasy pochodnego zestawu rekordów, aby zarządzać powiązaniem. Zobacz [zestaw rekordów artykułów: dynamiczne wiązanie kolumn danych (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||

## <a name="see-also"></a>Zobacz też

[Kompilowanie na platformie](../mfc/building-on-the-framework.md)<br/>
[Sekwencja operacji do kompilowania aplikacji MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[Sekwencja operacji na potrzeby tworzenia aplikacji OLE](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[Sekwencja operacji do tworzenia kontrolek ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)
