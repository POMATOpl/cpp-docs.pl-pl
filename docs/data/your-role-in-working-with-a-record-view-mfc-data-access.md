---
description: 'Dowiedz się więcej na temat: Twoja rola w pracy z widokiem rekordu (dostęp do danych MFC)'
title: Twoja rola w pracy z widokiem rekordu (dostęp do danych MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
ms.openlocfilehash: f1eff5db930859ca1956286a9364c72b02f2b473
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302611"
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>Twoja rola w pracy z widokiem rekordu (dostęp do danych MFC)

W poniższej tabeli przedstawiono, co zwykle trzeba wykonać, aby korzystać z widoku rekordu oraz od tego, co platforma robi.

### <a name="working-with-a-record-view-you-and-the-framework"></a>Praca z widokiem rekordu: ty i struktura

|Ty|Struktura programu|
|---------|-------------------|
|Aby zaprojektować formularz, użyj edytora okien dialogowych Visual C++.|Tworzy zasób szablonu okna dialogowego z kontrolkami.|
|Użyj [Kreatora aplikacji MFC](../mfc/reference/database-support-mfc-application-wizard.md) , aby utworzyć klasy pochodne z [formularzy CRecordView](../mfc/reference/crecordview-class.md) i [CRecordset](../mfc/reference/crecordset-class.md).|Zapisuje klasy dla Ciebie.|
|Mapuj kontrolki widoku rekordu na elementy członkowskie danych pola zestawu rekordów.|Zawiera DDX między kontrolkami i polami zestawu rekordów.|
||Udostępnia domyślne programy obsługi poleceń do **przeniesienia w pierwszej kolejności**, **przenoszenia ostatniego**, **przenoszenia dalej** i **przenoszenia poprzednich** poleceń z menu lub przycisków paska narzędzi.|
||Aktualizuje zmiany w źródle danych.|
|Obowiązkowe Napisz kod, aby wypełnić pola listy lub pola kombi albo inne kontrolki z danymi z drugiego zestawu rekordów.||
|Obowiązkowe Napisz kod dla wszelkich specjalnych walidacji.||
|Obowiązkowe Napisz kod, aby dodać lub usunąć rekordy.||

Programowanie oparte na formularzach to tylko jedno podejście do pracy z bazą danych. Aby uzyskać informacje o aplikacjach korzystających z innego interfejsu użytkownika lub bez interfejsu użytkownika, zobacz [MFC: używanie klas baz danych z dokumentami i widokami](../data/mfc-using-database-classes-with-documents-and-views.md) oraz [MFC: używanie klas baz danych bez dokumentów i widoków](../data/mfc-using-database-classes-without-documents-and-views.md). Aby poznać alternatywne podejścia do wyświetlania rekordów bazy danych, zobacz klasy [CListView](../mfc/reference/clistview-class.md) i [CTreeView](../mfc/reference/ctreeview-class.md).

## <a name="see-also"></a>Zobacz też

[Widoki rekordów (dostęp do danych MFC)](../data/record-views-mfc-data-access.md)<br/>
[Lista sterowników ODBC](../data/odbc/odbc-driver-list.md)
